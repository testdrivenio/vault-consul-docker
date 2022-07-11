# Managing Secrets with Vault and Consul

## Want to learn how to build this?

Check out the [post](https://testdriven.io/managing-secrets-with-vault-and-consul).

## Want to use this project?

1. Fork/Clone
2. Generate ssl
```
apt-get install openssl
openssl genrsa -aes256 -out certificat.key 4096
mv certificat.key certificat.key.lock
openssl rsa -in certificat.key.lock -out certificat.key
openssl req -new -key certificat.key.lock -out certificat.csr
openssl x509 -req -days 365 -in certificat.csr -signkey certificat.key.lock -out certificat.crt
```
4. Build the images and run the containers:

    ```sh
    $ docker-compose up -d --build
    ```

1. You can now interact with both Vault and Consul. View the UIs at [https://localhost:8200/ui](https://localhost:8200/ui) and [https://localhost:8500/ui](https://localhost:8500/ui).
