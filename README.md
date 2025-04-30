# How does SSL work? | SSL certificates and TLS
SSL stands for Secure Sockets Layer, and it refers to a protocol for encrypting, securing, and authenticating communications that take place on the Internet. Although SSL was replaced by an updated protocol called TLS (Transport Layer Security) some time ago, "SSL" is still a commonly used term for this technology.

The main use case for SSL/TLS is securing communications between a client and a server.

## How does SSL/TLS work?

- Secure communication begins with a TLS handshake, in which the two communicating parties open a secure connection and exchange the public key
  ### What happens during a TLS handshake?
          During the course of a TLS handshake, the client and server together will do the following:
          Specify which version of TLS (TLS 1.0, 1.2, 1.3, etc.) they will use
          Decide on which cipher suites they will use
          Authenticate the identity of the server via the server’s public key and the SSL certificate authority’s digital signature
          Generate session keys in order to use symmetric encryption after the handshake is complete
- During the TLS handshake, the two parties generate session keys, and the session keys encrypt and decrypt all communications after the TLS handshake.
- Different session keys are used to encrypt communications in each new session.
- TLS ensures that the party on the server side, or the website the user is interacting with, is actually who they claim to be.
- TLS also ensures that data has not been altered, since a message authentication code (MAC) is included with transmissions.

TLS communication sessions begin with a TLS handshake. A TLS handshake uses something called **asymmetric encryption**, meaning that two different keys are used on the two ends of the conversation. This is possible because of a technique called public key cryptography.

In public key cryptography, two keys are used: a public key, which the server makes available publicly, and a private key, which is kept secret and only used on the server side. Data encrypted with the public key can only be decrypted with the private key.

During the TLS handshake, the client and server use the public and private keys to exchange randomly generated data, and this random data is used to create new keys for encryption, called the session keys.

### Symmetric encryption with session keys

Unlike asymmetric encryption, in symmetric encryption the two parties in a conversation use the same key. After the TLS handshake, both sides use the same session keys for encryption. **Once session keys are in use, the public and private keys are not used anymore**. Session keys are temporary keys that are not used again once the session is terminated. A new, random set of session keys will be created for the next session.

