# assignment_demo_2023

![Tests](https://github.com/TikTokTechImmersion/assignment_demo_2023/actions/workflows/test.yml/badge.svg)

This is a submission for backend assignment of 2023 TikTok Tech Immersion.

Workflow
1. The client (user) will first make an HTTP call to the HTTP server. The main purpose of the HTTP server is just to process HTTP requests and responses. Most of the business logic is done in microservices, which reside in the rpc-server for our design.
2. The HTTP server makes an RPC call to the rpc-server in the local network. (External clients can't access this rpc-server directly).
3. The rpc-server receives and processes the request. This can either be SendRequest() or PullRequest() in our case.
4. SendRequest will write messages to the Redis server while PullRequest will read messages from Redis.
5. This data is passed back to the HTTP server to return to the client as an HTTP response.

Tasks

Most of the server codes were already implemented in the demo template. There are only a few modifications left:

1 Setup and configure a datastore. In ths case, we were recommended to make use of Redis for the database. 
2. Edit the docker-compose.yml to add a Redis server
3. Setup Redis client in the rpc-server
4. Implement handlers in rpc-server.
   We had to replace areYouLucky() function with our own business logic, i.e writing and reading messages from Redis.



