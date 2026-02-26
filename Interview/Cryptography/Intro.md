# Cryptography

* Cryptography is the science of protecting information using mathematical technqiues to ensure confidentiality, integrity, and authetication.
* It transforms readable data into unreadable form, prventing unauthrized access and tampering.

## Types of Cryptography

### 1. Symmetric Key Cryptography
* Sender and receiver of a message use a single common key to encrypt and decrypt messages.
* It is faster and simpler but the problem is sender and receiver have to somehow  exchange keys securely.
* The most popular symmetric key cryptography system are Data Encryption(DEC) and Advance Encryption System(AES).

<div>
  <img width="988" height="363" alt="image" src="https://github.com/user-attachments/assets/03502f2a-2997-4bae-a9d3-c598434f19b1" />
</div>

### 2. Asymmetric KEy Cryptography
* In Asymmetric Key Cryptography a pair of keys is usesd to encrypt and decrypt information. A sender's public key is used for encryption and receivers private key is used for decryption.
* Even everyone know the public key, the decryption is only can only be done by the indended receiver by the private key.
* Example: RSA
* Symmetric keys are slow, and inefficient and can ony be used with small amount of data.
* What we can do is we can share the symmetric keys using Assymetric Key Encrption and then after can use symmetric Key Encryption to share bulk data. This is what SSL and TLS do

<div>
  <img width="650" height="325" alt="image" src="https://github.com/user-attachments/assets/d00c78a6-9637-4172-8ed5-84eb95eb4320" />
</div>

#### Public and Private Keys

* Think of public and private keys as a high-tech mailbox system. Anyone can have your address and drop a letter through the slot(Public Key), but only you have the physical key(Private key) to open the box and read the mail.
* Public: The Public key encrypts the data
* The Private Key: It can decrypt the data encrypted by the public key.

### 3. Hash Functions
