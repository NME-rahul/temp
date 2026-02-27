# Authentication

* Suppose a Scenario that Pam wants to send the "Hello" msg to Jim.
* Pam will share his Publick-key with Jim.
* Now Pam will encrypt the data with her Private-Key, now only her Public-key can decrypt it so Whoever have Pam's Public Key can decrypt, it ensures that only Private-Key holder can encrypts and she is Pam.

* # Integrity

  * Assymetric Keys can be used to ensure the integrity of Data meaning they are not modifed by some middle-men.
  * Because the shared data is encrypted data can only be decrypted by the Public-Key, the public key holder can decrypt and see if the decrypted data is grbage either data is compromised or user is not authentic.

---

* Autheticaation process for Signature, By signatue with Private-Key we can ensure that only Privat-key holder can encrypt by decrypting.
