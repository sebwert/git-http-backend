A dead simple git smart-http server using nginx as a frontend. No authentication, no SSL, push is free-for-all.

> _caveat emptor_ this is not intended for production use

Usage:

```
docker run -d -p 4080:80 -v /path/to/host/gitdir:/git gocdcontrib/git-http-backend:v2
```

Unauthenticated push will not work unless you enable it in repositories:

```
cd /path/to/host/gitdir
git init --bare test.git
cd test.git
git config http.receivepack true
```

Source for Docker images at: https://hub.docker.com/r/gocdcontrib/git-http-backend/tags/

For docker image with tag v2, the repo digest is: gocdcontrib/git-http-backend@sha256:851766e546665ac795997a140128fddd73a347b5eb665684bfad3b91f7cadbda
