# copelco.me

My [Hugo site](https://gohugo.io/) using the [Congo theme](https://github.com/jpanther/congo)

Setup

```sh
go install -tags extended github.com/gohugoio/hugo@latest
```

Run:

```sh
hugo server -D
hugo server --buildDrafts
```

Run Docker:

```sh
docker compose up -d
```

New site:

```sh
docker compose run --rm hugo new site .
docker compose run --rm hugo mod init my-project
docker compose exec hugo hugo shell
hugo:/src$ cp -r /tmp/modules/filecache/modules/pkg/mod/github.com/jpanther/congo/v2@v2.4.2/config/_default/* /src/config/_default/
```
