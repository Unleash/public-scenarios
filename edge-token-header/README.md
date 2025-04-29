This scenario sets up Unleash and Edge.

It simulates having an intermediate proxy between Edge and Unleash that rewrites the Custom token header used in Edge to Unleash's expected `Authorization` header.

## How to run
Run `docker-compose up`

## How to see the logs from the nginx proxy
Run `tail -f nginx-logs/access.log` and look at the custom header EdgeAuth

## How to send a frontend request to edge
```shell
curl -H'EdgeAuth: *:production.d8871cf9d80712c6b747ab296b74d02f2a9cef91f0f93b26ec8979fd' http://localhost:3063/api/frontend
```

## How to send the same request directly to unleash
```shell
curl -H'Authorization: *:production.d8871cf9d80712c6b747ab296b74d02f2a9cef91f0f93b26ec8979fd' http://localhost:4242/api/frontend
```
