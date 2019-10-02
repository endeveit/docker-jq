# docker-jq
Docker image for [jq](http://stedolan.github.io/jq/) based on [alpine linux](https://alpinelinux.org/) image, just over 4MB in size.

This image also contains [curl](https://curl.haxx.se/) to make HTTP requests.

## Usage

Test `jq` command:

```bash
$ docker run --rm --name jq endeveit/docker-jq \
  sh -c 'echo "{\"foo\":\"bar\"}" | jq .'
{
  "foo": "bar"
}
```

Test a complex command:

```bash
$ docker run --rm --name jq endeveit/docker-jq \
  sh -c 'echo "{\"foo\":\"bar\"}" | jq ". | .foo as \$var | \$var"'
"bar"
```

Start an interactive container with jq:

```
$ docker run -it --rm --name jq endeveit/docker-jq
```

This will drop into `/bin/sh`, then `jq` command can be run:

```bash
# jq
```
