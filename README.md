# frntn/locust

Docker container for `locust` load testing tool

## Usage

### Basic Usage

Just create an alias to start the container and use it as the standard locust command without any environment issue.

```
alias locust='docker run --rm -v $PWD:/usr/src/app frntn/locust'
locust --help
```

### Advanced Usage

If you want to get into the container for debugging use `--entrypoint`

## Limitation

If you start locust with `-f` the file location will have to be a relative path **and** _under_ the current working directory.
