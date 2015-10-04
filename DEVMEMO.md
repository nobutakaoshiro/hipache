# Generate Self-signed Server Certificate

```bash
cd ssl

# generate private key (no password)
openssl genrsa -out ssl.key 2048

# generate CSR
openssl req -new -key ssl.key -out ssl.csr

# generate self-signed server certificate
openssl x509 -days 3650 -req -signkey ssl.key < ssl.csr > ssl.crt
```

## CSR Information Example

```bash
$ openssl req -new -key ssl.key -out ssl.csr
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:JP
State or Province Name (full name) [Some-State]:Tokyo
Locality Name (eg, city) []:Shinjuku-ku
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Example K.K.
Organizational Unit Name (eg, section) []:Development Dept.
Common Name (e.g. server FQDN or YOUR name) []:www.example.com
Email Address []:

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:
```