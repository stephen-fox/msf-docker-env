# metasploit docker-compose environment
This is a slightly modified docker-compose configuration based on the file
found in [rapid7's repository](https://github.com/rapid7/metasploit-framework/blob/master/docker-compose.yml).

I wanted to document how this works and make some small tweaks to their
configuration - so here we are!

## Prerequisites
You must set the `POSTGRES_PASSWORD` environment variable before using this.
You can do this using `read`:

```
read -s POSTGRES_PASSWORD
# Type in some random garbage.
export POSTGRES_PASSWORD
```

You will also need to install Docker engine and `docker-compose`.

## Usage
The following examples demonstrate how to use the environment.

#### Start metasploit with incomming connections disabled
```
docker-compose run ms
```

#### Start metasploit and permit listening on default ports in the config file
```
docker-compose run --service-ports ms
```

#### Start metasploit and specify mapping 8080 on host to 8080 on container
```
docker-compose run -p 8080:8080 ms
```

#### Start metasploit and specify several port mappings
```
docker-compose run -p 8080:8080 -p 8443:8443 ms
```
