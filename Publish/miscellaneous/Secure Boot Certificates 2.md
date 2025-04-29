you accidentally deleted your certificates for Secure Boot and need to reassign them, you can follow the steps below to regenerate and reassign the necessary certificates. This involves creating a new certificate, enrolling it with the `mokutil` tool, and signing any necessary kernel modules or bootloader binaries. Here's how you can proceed:

### Step 1: Generate a New Secure Boot Key Pair

You need to regenerate your Secure Boot key pair (private and public certificates). You can use `openssl` for this.

1. **Create an OpenSSL configuration file (`openssl.cnf`)** for certificate creation. Here is an example configuration:
    
    ```ini
    HOME                    = .
    RANDFILE                = $ENV::HOME/.rnd
    [ req ]
    distinguished_name      = req_distinguished_name
    x509_extensions         = v3
    string_mask             = utf8only
    prompt                  = no
    
    [ req_distinguished_name ]
    countryName             = CA
    stateOrProvinceName     = Quebec
    localityName            = Montreal
    0.organizationName      = cyphermox
    commonName              = Secure Boot Signing
    emailAddress            = example@example.com
    
    [ v3 ]
    subjectKeyIdentifier    = hash
    authorityKeyIdentifier  = keyid:always,issuer
    basicConstraints        = critical,CA:FALSE
    extendedKeyUsage        = codeSigning,1.3.6.1.4.1.311.10.3.6,1.3.6.1.4.1.2312.16.1.2
    nsComment               = "OpenSSL Generated Certificate"
```
    
    Update the `commonName` field and other fields as needed.
    
2. **Generate the certificate** using `openssl`:
    
    ```bash
    openssl req -config ./openssl.cnf \
                -new -x509 -newkey rsa:2048 \
                -nodes -days 36500 -outform DER \
                -keyout "MOK.priv" \
                -out "MOK.der"
    ```
    
    This will generate the following:
    
    - `MOK.priv`: Your private key
    - `MOK.der`: Your public key in DER format

### Step 2: Enroll the Key in Secure Boot

Next, you'll need to enroll the generated public key (`MOK.der`) in the system's Secure Boot keyring using the `mokutil` tool.

1. **Import the public key into the MOK (Machine Owner Key) database**:
    
    ```bash
    sudo mokutil --import MOK.der
    ```
    
2. **Set a password** when prompted, which will be required during the enrollment process.
    
3. **Reboot your system**.
    
4. **Enroll the key** during boot:
    
    - When your system restarts, you should see a screen from the **MokManager** (a component of shim).
    - Select the option `Enroll MOK` and follow the prompts to complete the enrollment process.
    - You will be asked to enter the password you set earlier.

### Step 3: Verify the Key Enrollment

After the system reboots, you can verify that the key is enrolled correctly by checking `/proc/keys`:

```bash
sudo cat /proc/keys
```

Look for a key associated with your `MOK.priv` certificate.

### Step 4: Sign Your Modules or EFI Files

Now that your key is enrolled, you can proceed to sign any kernel modules or EFI binaries that need to be signed.

1. **To sign kernel modules**:
    
    ```bash
    kmodsign sha512 MOK.priv MOK.der module.ko
    ```
    
    Replace `module.ko` with the actual kernel module file you wish to sign.
    
2. **To sign EFI binaries (e.g., a custom kernel)**:
    
    First, convert your certificate to PEM format:
    
    ```bash
    openssl x509 -in MOK.der -inform DER -outform PEM -out MOK.pem
    ```
    
    Then, sign your binary with `sbsign`:
    
    ```bash
    sbsign --key MOK.priv --cert MOK.pem my_binary.efi --output my_binary.efi.signed
    ```
    
    Replace `my_binary.efi` with the actual EFI binary file you wish to sign.
    

### Step 5: Reboot and Verify

Once the signing process is complete, reboot your system to ensure that the newly signed modules and/or EFI binaries load properly under Secure Boot.

---

### Important Notes:

- Make sure you **keep track of your private keys** (such as `MOK.priv`) and never lose them, as they are necessary for signing new modules or binaries in the future.
- You can also **automate the signing process** using tools like `DKMS` to automatically sign modules on installation if you are frequently working with custom modules.
- If you use third-party modules or EFI binaries (such as those provided by hardware manufacturers), you will need to sign those as well before they can be loaded by Secure Boot.

Let me know if you run into any issues or need further clarification!