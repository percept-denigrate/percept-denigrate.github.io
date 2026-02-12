TLS (transport layer security) is a layer 6 protocol used to encrypt [[HTTP]] communications. The goal is to initially use asymmetric cryptography to securely obtain a shared secret key, and then to use this key in symmetric cryptography, in order to have both the security of asymmetric cryptography and the speed of symmetric cryptography.

The first step is authentication through the handshake:
- The client sends an initial request to the server, containing supported TLS versions and a random number.
- The server sends the chosen TLS version, a random number, the client's number signed with the server's private key, and its [[TLS certificate]]. 
- The client checks the signature, and sends the server's number signed with the client's private key

It then uses an asymmetric algorithm to derive symmetric keys. Older versions used [[RSA]], but modern versions have moved on to [[Diffie-Hellman]] and [[ECDH]].