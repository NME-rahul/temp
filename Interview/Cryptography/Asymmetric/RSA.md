# RSA(Rivest, Shamir, Adleman)

#### Totient or $\phi(n)$ or $phi(n)$
* It measures brackabiliy of a number.
* Totient of a number $n$ is count of all number $\leq n $, that share no common factor(relatively prime) with $n$.
* in other words, Count of all $K$ in range $1 \leq K \leq n$, such that for any number $K$, $gcd(n, K) = 1$
* For any prime number since there exist no factor so count of all number less then $n$ are Totient of $n$ that is $n-1$; $phi(n) = n - 1$ where $n$ is Prime.
* Since produce of any two Prime numbers also have two factor by which they are formed; $phi(n) = phi(p) * phi(q)$ when $N = p \times q$ and $p$ and $q$ are Prime.


## Maths Behine RSA
1. Randomly Choose two Prime Numbers $p, q$
2. Calculate their product $N = p \times q$
3. Calculate Totient $T = (p-1) * (q - 1)$
4. Select Public-Key $E$
   * It must be Prime
   * Must be less than Totient $T$
   * Must NOT be a factor of the Totient $T$
5. Select a Private-Key $D$
   * Product of $D$ and E$, divided by $T$ must result in a remainder of $1$.
   * $(D * E) \\ \\ MOD \\ \\ T$ = 1
  
* we have now Public-Key and Private-Key

6. Encryption: $(Message)^E \\ \\ MOD \\ \\ N =$ Cipher-Text
7. Decryption: $(Cipher-Text)^D \\ \\ MOD \\ \\ N =$ Original-message


### Use Cases of RSA

* Secure Web Browsing(HTTPS/SSL/TLS)
* Digital Signature
* Email Encryption
* Secure File Transfer(SFTP)
* Virtual Private Networks(VPNs)
* Key Exchange
* Blockchain
