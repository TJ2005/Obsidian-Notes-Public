```python
import itertools

# 1. Caesar Cipher
def caesar_encrypt(plaintext, shift):
    result = ""
    for char in plaintext:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            result += chr((ord(char) - shift_base + shift) % 26 + shift_base)
        elif char.isdigit():
            result += str((int(char) + shift) % 10)  # Handle digits as well
        else:
            result += char
    return result

def caesar_decrypt(ciphertext, shift):
    return caesar_encrypt(ciphertext, -shift)

# 2. Vigenère Cipher
def vigenere_encrypt(plaintext, key):
    key = key.upper()
    result = ""
    key_index = 0
    for char in plaintext:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            shift = ord(key[key_index % len(key)]) - 65
            result += chr((ord(char) - shift_base + shift) % 26 + shift_base)
            key_index += 1
        elif char.isdigit():
            result += str((int(char) + int(key[key_index % len(key)])) % 10)
            key_index += 1
        else:
            result += char
    return result

def vigenere_decrypt(ciphertext, key):
    key = key.upper()
    result = ""
    key_index = 0
    for char in ciphertext:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            shift = ord(key[key_index % len(key)]) - 65
            result += chr((ord(char) - shift_base - shift + 26) % 26 + shift_base)
            key_index += 1
        elif char.isdigit():
            result += str((int(char) - int(key[key_index % len(key)])) % 10)
            key_index += 1
        else:
            result += char
    return result

# 3. Atbash Cipher
def atbash_encrypt_decrypt(text):
    result = ""
    for char in text:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            result += chr(25 - (ord(char) - shift_base) + shift_base)
        elif char.isdigit():
            result += str(9 - int(char))  # Reverse digits as well
        else:
            result += char
    return result  # Same function works for both encryption and decryption

# 4. Playfair Cipher
# Use simple substitution for this example as Playfair is complex for this purpose.

# 5. Rail Fence Cipher
def rail_fence_encrypt(plaintext, rails):
    fence = [['' for _ in range(len(plaintext))] for _ in range(rails)]
    rail = 0
    var = 1

    for i, char in enumerate(plaintext):
        fence[rail][i] = char
        rail += var
        if rail == 0 or rail == rails - 1:
            var = -var

    return ''.join(''.join(row) for row in fence)

def rail_fence_decrypt(ciphertext, rails):
    fence = [['' for _ in range(len(ciphertext))] for _ in range(rails)]
    index = 0
    rail = 0
    var = 1

    for r in range(rails):
        for i in range(len(ciphertext)):
            if rail == r:
                fence[rail][i] = '?'
            rail += var
            if rail == 0 or rail == rails - 1:
                var = -var
        rail = 0
        var = 1

    for r in range(rails):
        for i in range(len(ciphertext)):
            if fence[r][i] == '?':
                fence[r][i] = ciphertext[index]
                index += 1

    rail = 0
    var = 1
    result = []
    for i in range(len(ciphertext)):
        result.append(fence[rail][i])
        rail += var
        if rail == 0 or rail == rails - 1:
            var = -var

    return ''.join(result)

# Function to calculate the key based on two sequences
def calculate_key(seq1, seq2):
    key = ""
    for i in range(len(seq1)):
        key += str((int(seq1[i]) - int(seq2[i])) % 10)  # Mod 10 to handle digits
    return key

# List to store found keys
keys = []

# Apply decryption with various ciphers using the key
def apply_ciphers(ciphertext, key):
    results = {}
    
    # Try Caesar Cipher
    for shift in range(10):
        decrypted = caesar_decrypt(ciphertext, shift)
        results[f'Caesar shift {shift}'] = decrypted
    
    # Try Vigenère Cipher
    decrypted = vigenere_decrypt(ciphertext, key)
    results[f'Vigenère with key {key}'] = decrypted
    
    # Try Atbash Cipher
    decrypted = atbash_encrypt_decrypt(ciphertext)
    results['Atbash'] = decrypted

    # Try Rail Fence Cipher (for various rails)
    for rails in range(2, 6):
        decrypted = rail_fence_decrypt(ciphertext, rails)
        results[f'Rail Fence with {rails} rails'] = decrypted
    
    return results

# Combination decryption with two algorithms
def apply_combinations(ciphertext, key):
    ciphers = ['Caesar', 'Vigenère', 'Atbash', 'Rail Fence']
    combinations = itertools.product(ciphers, repeat=2)
    results = {}

    for comb in combinations:
        cipher1, cipher2 = comb
        intermediate = apply_ciphers(ciphertext, key).get(cipher1)
        if intermediate:
            final_decrypt = apply_ciphers(intermediate, key).get(cipher2)
            if final_decrypt:
                results[f'{cipher1} + {cipher2}'] = final_decrypt
    
    return results

# Main execution
if __name__ == "__main__":
    ciphertext = "MZNAT JSTJTSIWEX"
    seq1 = "8967853238"
    seq2 = "8962853938"

    # Calculate the key from the two sequences
    key = calculate_key(seq1, seq2)
    print(f"Calculated Key: {key}")

    # Append the key to the list of found keys
    keys.append(key)

    # Apply single cipher decryption
    single_cipher_results = apply_ciphers(ciphertext, key)
    print("Single Cipher Decryption Results:")
    for cipher, result in single_cipher_results.items():
        print(f"{cipher}: {result}")

    # Apply two ciphers in combination
    combination_results = apply_combinations(ciphertext, key)
    print("\nCombination Cipher Decryption Results:")
    for combo, result in combination_results.items():
        print(f"{combo}: {result}")

```
