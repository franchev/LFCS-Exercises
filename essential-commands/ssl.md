# SSL is actually TLS

SSL -> Secure sockets layer
TLS -> Transport layer Security


SSL certificate is a data file that lets websites use HTTPS, which is the secure http. This certificate is hosted on the website's origin server and contains the website's public key, identity, and other information. So when a person tries to access this website, it uses the SSL certificate to get the public key and verify the server's identity preventing malicious activities. SSL certificates also create encryption.

openssl is the tool to use to generate ssl (really tls) certificates.

Here are a few terms that you will come across that are important to understand. 

* CSR: certificate signing request is needed to get own own SSL/TLS certificate. CSR contains information such as common name, organization, certificate authority to use to create your cert.
* Common Name (CN):  This is the hostname for which an SSL certificate is issued for. You can use the entire hostname: www.example.com. You can also use wildcard represented by the asterics: *.example.com
* Private keys: decrypts the data
* public keys: encrypts the data -> SSL uses public key cryptography to establish secure communication over the internet.
* Certificate Authority (CA): is a trusted entity that issues SSL certificates (i.e Digicert) 
* Self-signed certs: This is not signed by a publicly trusted CA but instead by the developer or company responsible for the website. These are unsave for public applications and websites.



### create a 4096-bit RSA private key and CSR using the openssl command


<details><summary>Answer</summary>

```bash
openssl req -newkey rsa:4096 -keyout private.key -out certifate.csr        
```

</details>


### Generate a self-signed certificate that will expire in a year Name it test-cert.crt. Set the common name to: test.example.com


<details><summary>Answer</summary>

```bash
openssl req -x509 -noenc -days 365 -keyout private.key -out test-cert.crt     
enter test.example.com for the common name
```

</details>


### view the content of a crt file


<details><summary>Answer</summary>

```bash
openssl x509 -text -in file.crt
```

</details>



