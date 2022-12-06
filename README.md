# Hugo Blog

A [Hugo site](https://gohugo.io/) using the [Congo theme](https://github.com/jpanther/congo)

Run:

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
