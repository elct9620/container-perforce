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

Security
---

Due to default configure is not security, you may want to do below configure.

#### Install Perforce Client

Before configure, you need to have `p4` command.

If you are using MacOSX, you can simple type `brew tap homebrew/binary && brew install perforce` to install it.

You may need to set perforce port to correctly connect server.

```
p4 set P4PORT=IP:1666
```

Note: you need replace IP to your Perforce Server IP Address

#### Disallow User Auto Creation

```
p4 configure set dm.user.noautocreate=2
```

#### User should have password

```
p4 configure set security=seclevel1
```
