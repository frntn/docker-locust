# frntn/locust

Docker container for `locust` load testing tool

## Usage

### Basic Usage

Create a `locustfile.py`

Start a container

```
# WEBUI: expose 8089 port, and enter number of vusers + hatch rate on http://localhost:8089
docker run --rm -p 8089:8089 -v $PWD:/usr/src/app frntn/locust                    -L INFO -H http://www.google.fr

# NOWEBUI: deactivate webui, and enter number of vuser + hatch rate on command line
docker run --rm              -v $PWD:/usr/src/app frntn/locust --no-web -c 1 -r 1 -L INFO -H http://www.google.fr
```

In fact you could just create an alias to start the container and use it as is :

```
alias locust='docker run --rm -p 8089:8089 -v $PWD:/usr/src/app frntn/locust'
locust -H http://example.com
locust -H http://www.google.fr --no-web -c 500 -r 15
...
```

### Advanced Usage

If you want to get into the container for debugging use `--entrypoint`

## Limitation

If you start locust with `-f` the file location will have to be a relative path **and** _under_ the current working directory.
