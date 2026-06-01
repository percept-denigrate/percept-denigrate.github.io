Copy fail (CVE-2026-31431) is a major [[Linux]] priviledge escalation vulnerability.

It happens when the attacker can corrupt the in-memory copy of a program in the [[Page cache]].

# AF_ALG

The `AF_ALG` socket is an interface between user sape and the kernel crypto API. It does some optimizations like copying data withing kernel space.

```
sock = socket.socket(socket.AF_ALG, )
```

When binding to it, you must specify `aead` (authentication and encryption with associated data) and its mode `authencesn(hmac(sha256),cbc(aes))`.

```
sock.bind(("aead","authencesn(hmac(sha256),cbc(aes))"))
```

# Authencesn

`authencesn` has a flaw.

It operated on a structure composed of:
- AAD (cleartext): metadata, headers, sequence numbers
- Ciphertext
- Message tag: contains checksum

The attack uses the decryption mechanism.

During decryption, the AAD and the cyphertext are in a buffer while the static message tag is in a page cache. The AAD and the cyphertext are copied, but the message tag is simply referenced. And since the output is writable (in-place decryption operations), the message tag is writable.