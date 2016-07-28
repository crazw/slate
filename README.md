crazw-docker-slate
==================


Build
-----
```
docker build -t crazw/slate .
```


Run command
----------

```
docker run -d --name slate \
	-p 4567:4567 \
	-v /Users/crazw/Github/docker/slate/slate/source/:/app/source \
	crazw/slate
```

Custom
------

In your source documentation folder (which looks like [this](https://github.com/tripit/slate/tree/master/source)), create a `Dockerfile` with the following contents:

	FROM tutum/slate

And a `docker-compose.yml` with the following contents:

    version: "2"
    services:
      slate:
        build: .
        ports:
         - "4567:4567"

Use Docker Compose to run it:

    docker-compose up --build

Go to `http://localhost:4567/` and you will see your new API beautiful documentation.


