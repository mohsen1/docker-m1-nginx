# Test Repo

Test Repo for demonstrating issues with networking with Docker running on Apple Silicon.

Here is the instruction for running the repo

## Make certs

Generate the keys using [`mkcert`](https://github.com/FiloSottile/mkcert)

```sh
mkdir -p certs
mkcert -key-file certs/localhost.key -cert-file certs/localhost.pem  "test-server.dev" localhost "::1"
```

## update `/etc/hosts`

Add `test-server.dev` to `/etc/hosts`

```
sudo grep -qxF "127.0.0.1 test-server.dev" /etc/hosts || sudo echo "127.0.0.1 test-server.dev" >>/etc/hosts
```

## `docker-compose up`

```
docker-compose up
```

## Visit the local dev server

Go to [https://test-server.dev](https://test-server.dev)