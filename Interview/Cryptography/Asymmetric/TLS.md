# TLS(Transport Layer Security)

* It is the modern, more secure successor to SSL.
* TLS uses a combination of symmetric and asymmetric cryptography, with assymetric keys we share the symmetric keys and by symmetric keys we share actual data, because it is not practical to share data with assymetric key encryption method because data is gnerally a large size.

## CA(Certificate Authority)
* A Certificate Authority(CA) is an entity that issues digital certificates conforming to the ITU Standard ofr Public Key Infrastructure(PKI).
* Digital Certificate certify the public key of the owner of their certificate.
* CA thererfore acts as a trusted third party that gives clients assurance they are connecting to a server operated by validated entity.

#### Working

* Before any data is set, your browser and the server perform a **TLS Handshake**.

1. Your browser says "Hello " to the server and asks for its ID.
2. The server sends its SSL certificated(which contains server's Public-Key.
3. Your Browser verfies the certificated to make sure the certificate is real and hasn't expired.
4. Your Browser then creates a temprory unique Session Key(Symmetric Key), encrypts it with the server's Public-Key and send it back.
5. Both the server and client now have Session-key shared using Public-Key of server and only server can decrypts it.
6. Both can now share data by encrypting/decrypting it with Session-key.
