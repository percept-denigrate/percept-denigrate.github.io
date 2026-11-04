A mathematical proof is an algorithm that convinces someone that a statement is true. A proof system is a procedure that decides whether a proof is accepted.

A proof system has 4 main properties:

- Completeness: any true statement has a proof of its validity
- Soundness: no false statement has a proof
- Efficient verification: simple statements have short proofs that can be checked quickly
- Efficient proof: simple statements have short proofs that can be found quickly

# Interactive proofs

Interactive proofs are based on asking the prover a question or giving it a task to do with the data.

For example: a cloud provider stores a customer's data, and the customer only stores a summary of it. The customer can ask questions about the data, the cloud provider computes the answer and sends it to the customer, who can then check it.

IPs are not transferable, the verifier can not use the prover's proof to prove the statement to a third party.

# Multi-provider interactive proofs and probabilistically checkable proofs

An MIP is like an IP, but with multiple provers who don't share information with one another regarding the challenges they receive.

PCPs use static proofs but the verifier can only read a small number of characters from the proof.
