

# Fernet Encryption & Decryption  

## Description  
This project demonstrates how to securely encrypt and decrypt messages using the **Fernet** symmetric encryption method from the `cryptography` library in Python.  

## Features  
✅ Secure message encryption using a generated key  
✅ Decryption back to the original message  
✅ Uses **Fernet** from the `cryptography` library  

## Installation  
Make sure you have the `cryptography` library installed:  
```sh
pip install cryptography
```

## Usage  

### 1. **Generate a Key & Encrypt a Message**
```python
from cryptography.fernet import Fernet

# Generate a key (store this safely!)
key = Fernet.generate_key()
f = Fernet(key)

# Encrypt a message
encrypt_token = f.encrypt(b"A really secret message. Not for prying eyes.")
print(encrypt_token)
```

### 2. **Decrypt the Message**
```python
# Decrypt the message
decrypt_token = f.decrypt(encrypt_token)
print(decrypt_token)  # Output: b'A really secret message. Not for prying eyes.'
```

## Sample Output  
```sh
b'gAAAAABlP8l...VY2XUObZRrX...'  # Encrypted token (varies every time)
b'A really secret message. Not for prying eyes.'  # Decrypted message
```

## Notes  
- The encryption output changes every time due to random initialization vectors (IVs).  
- Always store the key securely; without it, decryption is impossible.  

