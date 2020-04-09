# self-signed-certs

This is a simplified demonstration of how to generate and use self-signed TLS
certificates in an NGINX configuration.

This demo is based on the instructions in the Digital Ocean tutorial [How To Create a Self-Signed SSL Certificate for Nginx in Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-16-04)
by the inimitable [Justin Ellingwood](https://www.digitalocean.com/community/users/jellingwood).

Self-signed certificates are not secure for production, but this approach may be
useful for local development environments.

Be sure to refer to the [tutorial by Justin Ellingwod](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-16-04)
for additional details and tips about how to configure NGINX to use TLS
certificates and openssl.

## Running the demo

1. Generate a new self-signed certificate by running the bash script [bin/generate-self-signed-cert.sh](./bin/generate-self-signed-cert.sh).
2. Bring up the docker-compose environment by running `docker-compose up`.
3. Visit [http://localhost](http://localhost).
4. Your browser should alert you that the cerficate is not secure. This is expected because it has not been signed by a root certificate authority. For the purposes of this demo, it should be OK to bypass the warning the browser presents to you and trust the certificate.
5. Once the browser trusts the self-signed certificate, visit [http://localhost](http://localhost) again. If things are working correctly, you should be permanently redirected to `https://localhost`.

