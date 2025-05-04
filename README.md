#  Digital Signature Demo with OpenSSL

This project is a basic demonstration of creating and verifying digital signatures using OpenSSL in a Linux environment. It was done as part of my AltSchool Cybersecurity coursework.

##  What This Project Demonstrates

- Generation of a private/public RSA key pair
- Signing a text file using the private key
- Verifying the signature using the public key
- Signature validation and detection of tampered messages

##  Tools Used

- OpenSSL
- Kali Linux Terminal
- Shell commands

##  Steps to Reproduce

1. **Generate Private Key (RSA 2048-bit, encrypted):**

```bash
openssl genpkey -algorithm RSA -out user_private_key.pem -aes256

2. **Extract Public Key: **
openssl pkey -in user_private_key.pem -pubout -out user_public_key.pem

3. **Create message file: **
echo "This is a drill, testing encryption" > message.txt

4. **Sign the message:**
openssl dgst -sha256 -sign user_private_key.pem -out documemt.sig message.txt

5. **Verify the Signature:**
openssl dgst -sha256 -verify user_public_key.pem -signature documemt.sig message.txt
(Verification was successsful)

6. **Tested integrity by modifying the message.txt content and verified signature, it failed
# Digital-Signature-demo
