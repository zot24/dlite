# DLite

## Building

install dependencies

```sh
brew install opam golang
opam init
eval `opam config env`
opam pin add qcow-format git://github.com/mirage/ocaml-qcow#master
opam install uri qcow-format
go get -u github.com/jteeuwen/go-bindata/...
```

update dependencies (use this if you've already built the project before)

```sh
git submodule foreach git pull origin master
opam update
opam upgrade
```

build the binary

```sh
go generate
go build
```

## TODO

- write uninstall command to remove daemon plist, resolver config, nfs exports, ssh config, and user's instance
- investigate what we need to support vpn users
- add routing rules to connect direct to containers
- look in to querying the docker daemon to allow resolving containers by name in the dns process (i.e. <container>.docker)
