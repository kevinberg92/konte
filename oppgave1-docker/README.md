## PGR301 2021 February Exam EX01

### Exercise 01-A
* To build the latest docker-image run the command:
```
docker build . --tag konte
```

Exercise 01-B
* To run the latest container image created (the name foo-bar is ambiguous, while the "konte:latest" uses the id/tag used in Ex-01-A) run the command:
 ```
 docker run -d --name foo-bar -p 8080:9999 konte:latest
```
It can then be accessed on localhost:8080.
The reason for the 404 not found or in some other cases you may get internal server error 500, is because the endpoint in DemoController is set to use a file called index.html when accessing localhost:xxxx/ and Docker cannot allocate the file. Such files should be under src/main/resources when building dockerimages else if you dont specify it / copy it in the second stage of the DockerFile like in this particular scenario. This was fixed by adding ```COPY index.html .``` on line 9 in the Dockerfile. For a bigger project the more obvious solution would be to create such directory to avoid the same problem re-occuring for other files.

