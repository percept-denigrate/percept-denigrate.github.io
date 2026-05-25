[[TLS|SSL]] pinning is a security mechanism in [[Android]] applications to protect against [[MitM]] attacks.

The server's [[TLS certificate]] public key is hardcoded in the application, and when the application connects to the server it checks the provided public key against the hardcoded one. The connection is only allow if the keys match.

It can be bypassed by overwriting the checking mechanism functions in Frida or APKtool.
