#cybersecurity-concepts 

Pubic key cryptography, aka asymmetric encryption.

Method uses two keys: 
1. A public key, which anyone can access and is openly shared, often through a public directory.
2. A private key which the owner must keep secret

To decrypt a message, a computer combines the sender's public key with its own private key. The public 

![[asymmetric-encryption-diagram.png]]
# Benefits
- Secure

# Cons 
- Slower due to mathematical processes
- Requires computing power
	- High demand of resources
- Less suitable for prolonged sessions

# Use Cases

[[Digital signatures]]
- Hash the Message
- Encrypt the Digest
- Attach and Send 
- Decode the Signature 
- Hash the Received Message 
- Verify integrity and authenticity
Emails 