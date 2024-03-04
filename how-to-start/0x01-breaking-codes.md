---
description: When cryptography is outlawed, bayl bhgynjf jvyy unir cevinpl.
---

# 0x01 - Breaking codes

Cryptography is the practice and study of secure communication techniques, which includes various methods of encoding and decoding information. In this guide, we'll cover some basic cryptographic algorithms using Python, and will break them.

***

## Caesar Cipher

The Caesar Cipher is a simple substitution cipher where each letter in the plaintext is shifted a certain number of places down or up the alphabet.

#### How It Works:

1. **Choose a Shift Number:**
   * Pick a number, let's call it the "shift" (or key). This number determines how much each letter in your message will move.
2. **Encrypt Your Message:**
   * Take each letter in your message and move it down the alphabet by the chosen shift.
   * If your shift is 3, 'A' becomes 'D,' 'B' becomes 'E,' and so on.
3. **Example:**
   * Original Message: "HELLO"
   * Shift: 3
   * Encrypted Message: "KHOOR"

#### Implementation

```python
def caesar_cipher(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            start = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - start + shift) % 26 + start)
        else:
            result += char
    return result

# Example usage
plaintext = "HELLO"
shift_amount = 3
ciphertext = caesar_cipher(plaintext, shift_amount)
print("Original Message:", plaintext)
print("Encrypted Message:", ciphertext)
```

#### Breaking Caesar CIpher

As there are only 27 possible keys (shifts) for English alphabet, we can simply bruteforce all the keys:

```python
def brute_force_caesar_cipher(ciphertext):
    for shift in range(1, 26):
        decrypted_text = ""
        for char in ciphertext:
            if char.isalpha():
                start = ord('A') if char.isupper() else ord('a')
                decrypted_text += chr((ord(char) - start - shift) % 26 + start)
            else:
                decrypted_text += char
        print(f"Shift {shift}: {decrypted_text}")

# Example usage
encrypted_message = "KHOOR"
print("Encrypted Message:", encrypted_message)
print("\nBrute Force Decryption:")
brute_force_caesar_cipher(encrypted_message)
```

***

## XOR (Exclusive Or)

The XOR cipher is a symmetric-key algorithm that uses the XOR (exclusive OR) operation to encrypt and decrypt data. It is a simple bitwise operation where each bit of the plaintext is XORed with the corresponding bit of the key.

Illustration of XOR operation:

```
Data         (8 bits):  01011011   (Data to be encrypted)
key          (8 bits):  10100101   (Secret key)
XOR Result   (8 bits):  11111110   (Decrypted data)
```

#### Implementation

```python
def xor_cipher(text, key):
    result = ""
    for i in range(len(text)):
        result += chr(ord(text[i]) ^ ord(key[i % len(key)]))
    return result

# Example usage
plaintext = "Hello, World!"
key = "secret"
ciphertext = xor_cipher(plaintext, key)
print("\nXOR Cipher:")
print("Plaintext:", plaintext)
print("Key:", key)
print("Ciphertext:", ciphertext)
```

#### Breaking XOR cipher

Cracking XOR can be difficult. If the key is long, the easiest way to crack it is to know part of the plaintext. For example, if image is encrypted, several first bytes are known (Magic Bytes)
