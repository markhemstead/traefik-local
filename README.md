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

### Update /etc/hosts
Add to bottom
```text
127.0.0.1 traefik api.muzzapi.local dashboard.muzzapi.local wali.muzz.local messenger.muzzapi.local
::1       traefik api.muzzapi.local dashboard.muzzapi.local wali.muzz.local messenger.muzzapi.local
```

#### Update .env files
Any references to http://localhost:{port} can be changed to https://<service>.muzzapi.local
