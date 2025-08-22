---
Title: "Digital Certificates"
Status: 
marker: 
tags: 
Date: "2025.07.25"
Time: "11:18"
---
# Digital Certificates & Verification of Integrity
A digital certificates used to verify the Integrity of the file that one has received. The function always gives the same output. Thus a change in output = Tampered.

## Digital Certificates
- **Digital Certificates Overview**:
  - Digital certificates are electronic documents used to prove the ownership of a public key.
  - They are an essential part of public key infrastructure (PKI) and are used to secure online communications and verify identities.
- **Types of Digital Certificates**:
  - **SSL/TLS Certificates**:
    - **Purpose**: Used to secure communications over a computer network, primarily for HTTPS.
    - **Usage**: Ensures that data transmitted between a web server and a browser remains encrypted and private.
    - **Details**: SSL (Secure Sockets Layer) and its successor, TLS (Transport Layer Security), are protocols for establishing authenticated and encrypted links.
  - **Code Signing Certificates**:
    - **Purpose**: Used by software developers to digitally sign applications and software programs.
    - **Usage**: Ensures that the software has not been altered or tampered with since it was signed.
    - **Details**: Helps users verify the authenticity and integrity of software downloads.
  - **Document Signing Certificates**:
    - **Purpose**: Used to sign documents, such as PDFs, to ensure their authenticity and integrity.
    - **Usage**: Allows users to digitally sign documents, providing assurance that the document has not been altered.
    - **Details**: Often used in legal, financial, and business environments to secure documents.
  - **Client Certificates**:
    - **Purpose**: Used to authenticate clients to a server.
    - **Usage**: Ensures that the client connecting to a server is indeed who they claim to be.
    - **Details**: Often used in secure email, VPN access, and other secure communications.
  - **Email Certificates**:
    - **Purpose**: Used to sign and encrypt email messages.
    - **Usage**: Ensures the authenticity and confidentiality of email communications.
    - **Details**: Often used in conjunction with S/MIME (Secure/Multipurpose Internet Mail Extensions).
  - **Root Certificates**:
    - **Purpose**: Used to verify the authenticity of other certificates.
    - **Usage**: Forms the basis of the trust chain in PKI.
    - **Details**: Issued by trusted Certificate Authorities (CAs) and are pre-installed in browsers and operating systems.
## Checksum
- **Data Division**:
  - Data is divided into equal subunits of fixed bit length, typically 16 bits.
- **Sum Calculation**:
  - These subunits are summed together using one's complement arithmetic.
- **Complementing**:
  - The resulting sum is then complemented (inverted).
- **Checksum Creation**:
  - This complemented sum is known as the checksum.
- **Transmission**:
  - The checksum is appended to the end of the original data unit.
  - The combined data unit and checksum are transmitted to the receiver.
- **Receiver Side**:
  - The receiver divides the data into the same fixed bit length subunits.
  - The subunits are summed using one's complement arithmetic, including the checksum.
  - If the data is error-free, the final sum should be zero.
- **Error Detection**:
  - If the final sum is not zero, it indicates that an error has occurred during transmission.
## Padding
- 

## Routing Control
- **Moving Packets via a distributed network:** In routing control we decide to send the packets via different different routes. 
	- If someone eaves drop a certain route they wont have the entire conversation mapped because the rest is mapped out.
- All 

## Notarization
- **Third Party Verifier:** The use of a trusted third party to assure certain properties of data exchange.
	- **
# References


###### Information
- date: 2025.07.25
- time: 11:18