###PGR301 2021 February Exam

Exercise 01-A
* To build the latest docker-image run the command:
```
docker build . --tag konte
```

Exercise 01-B
* To run the latest container image created (the name foo-bar is ambiguous, while the "konte:latest" uses the id/tag used in the previous exrcise) run the command:
 ```
 docker run -d --name foo-bar -p 8080:9999 konte:latest
```
It can then be accessed on localhost:8080.
The reason for the 404 not found is because the endpoint in DemoController is set to use a file called index.html when accessing localhost:xxxx/ and Docker cannot allocate the file if you dont specify it in the second stage of the DockerFile. This was fixed by adding ```COPY index.html .``` on line 9 in the Dockerfile.

