# Generate cert
**SAN cert (webhook only use this)**
    
See here:
[Generate Certificates Manually](https://kubernetes.io/docs/tasks/administer-cluster/certificates/)


---

### key

Encrypt a private key:

```bash
openssl rsa -aes256 -in server.key -out server.key
```

Decrypt a private key:

```bash
openssl rsa -in server.key -out server.key
```

### cert

Encrypt a certificate:

```bash
openssl enc -aes256 -in server.crt -out server.crt
```

Decrypt a certificate:

```bash
openssl enc -d -aes256 -in server.crt -out server.crt
```

**base64**
```bash
base64 -w0 server.key > key.txt
base64 -w0 server.crt > cert.txt
base64 -w0 ca.crt > ca.txt
```