###PGR301 2021 February Exam

Exercise 01-A
* To build the latest docker-image run the command(note: the tag is ambiguous):
```
docker build . --tag foo
```

Exercise 01-B
* To run the latest container image created (the name foo-bar is ambiguous, while the "latest:foo" uses the id created from the previous exercise "--tag foo") run the command:
 ```
 docker run -d --name foo-bar -p 8080:9999 foo:latest
```

