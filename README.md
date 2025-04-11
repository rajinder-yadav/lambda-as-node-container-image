# AWS Lambda as a Node.js Container Image

## Build the Conrainer Image

```sh
docker build --platform linux/amd64 -t lambda-nodejs:test .
```

## Run the Container Image

```sh
docker run --rm --name lambda-nodejs --platform linux/amd64 -p 9000:8080 lambda-nodejs:test
```

## Invoke the Function

```sh
curl "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{"key": "value"}'
```

## Miscellaneous Commands

```sh
docker exec -it <container_id> /bin/sh
aws lambda invoke --function-name my-function output.json
```
