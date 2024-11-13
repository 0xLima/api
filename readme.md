# Kodo Exchange HTTP API 🥁

Kodo Exchange HTTP API is used by our app to fetch tokens and liquidity
pool pairs.

Please make sure you have [Docker](https://docs.docker.com/install/) first.

To build the image, run:
```
docker build ./ -t primaswap/api
```

Next, make a copy of the `env.example` file, and update the relevant variables.

Finally, to start the container, run:
```
docker run --rm --env-file=env.example.copy -v $(pwd):/app -p 8080:8080 -w /app -it primaswap/api
```

To run the syncer (refreshes data from chain) process, run:
```
docker run --rm --env-file=env.example.copy -v $(pwd):/app -p 8080:8080 -w /app -it primaswap/api sh -c 'python -m app.pairs.syncer'
```
