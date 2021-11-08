# Docker Best Practices Workshop

In a hands-on approach, we will cover 18 best practices in 4 categories or in other words **✅️ Dos & 🚫 Don'ts**.

Please note, this workshop assumes that you have a basic knowledge of Docker.

For the slides and recording: [Docker Best Practices Workshop](https://tech.aabouzaid.com/2021/09/docker-best-practices-workshop-presentation.html).


## The Application

The application source code is copied from [Docker Sample Application](https://docs.docker.com/get-started/02_our_app/)

It's a simple todo list manager that is running in Node.js, however, no real JavaScript experience is needed.
We will just run it.


## The Goal

The [Dockerfile](./app/Dockerfile) is updated it with the best practices.

### Build

Prod image:
```
docker build . -t docker-sample-app:v1 --target=prod
```

Dev image:
```
docker build . -t docker-sample-app:dev-v1 --target=dev
```

Test image:
```
docker build . -t docker-sample-app:test-v1 --target=test
```

### Run
```
docker run -p 3000:3000 docker-sample-app:v1
```

View:

http://localhost:3000


## Cheat Sheet

### Essential Practices
- Use Dockerfile linter
- Check Docker language specific best practices
- Create a single application per Docker image
- Create configurable ephemeral containers

### Image Practices
- Use optimal base image
- Pin versions everywhere
- Create image with the optimal size
- Use multi-stage whenever possible
- Avoid any unnecessary files

### Security Practices
- Always use trusted images
- Never use untrusted resources
- Never store sensitive data in the image
- Use a non-root user
- Scan image vulnerabilities

### Misc Practices
- Leverage Docker build cache
- Avoid system cache
- Create a unified image across envs
- Use ENTRYPOINT with CMD
