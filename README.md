Docker Perforce
===============

Docker image include perforce server.

Usage
---

#### Simple run Perforce Server

```
docker run --name p4d -p 1666:1666 -t elct9620/perforce
```

#### Keep Perforce Database

```
docker -run --name p4d -v $(pwd)/database:/perforce -p 1666:1666 -t elct9620/perforce
```

