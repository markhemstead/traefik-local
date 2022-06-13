## Installation

```shell
$ git clone https://github.com/markhemstead/traefik-local.git
$ cd traefik-local
$ docker network create traefik
$ docker-compose up -d
```

### Install mkcert to take advantage of local SSL
```shell
$ brew install mkcert
$ mkcert -install
$ cd certs/
$ mkcert -cert-file cert.csr -key-file priv.key muzzapi.local *.muzzapi.local muzz.local *.muzz.local
$ cat priv.key cert.csr > bundle.pem
```
