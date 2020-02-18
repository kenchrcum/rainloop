# kenchrcum/rainloop

![](https://i.goopics.net/nI.png)

### What is this ?

This is a fork from https://github.com/hardware/rainloop aiming to maintain a docker image running rainloop in the latest version.

Rainloop is a simple, modern & fast web-based client. More details on the [official website](http://www.rainloop.net/).

### Features

- Lightweight & secure image (no root process)
- Based on Alpine
- Latest Rainloop **Community Edition** (stable)
- Contacts (DB) : sqlite, mysql or pgsql (server not built-in)
- With Nginx and PHP7
- Postfixadmin-change-password plugin

### Build-time variables

- **GPG_FINGERPRINT** : fingerprint of signing key

### Ports

- **8888**

### Environment variables

| Variable | Description | Type | Default value |
| -------- | ----------- | ---- | ------------- |
| **UID** | rainloop user id | *optional* | 991
| **GID** | rainloop group id | *optional* | 991
| **UPLOAD_MAX_SIZE** | Attachment size limit | *optional* | 25M
| **LOG_TO_STDOUT** | Enable nginx and php error logs to stdout | *optional* | false
| **MEMORY_LIMIT** | PHP memory limit | *optional* | 128M

### Docker-compose.yml

```shell
git clone https://github.com/kenchrcum/rainloop.git
cd rainloop
docker build -t rainloop_1.14.0 .
```
```yml
rainloop:
image: rainloop_1.14.0
restart: always
volumes:
  - ./rainloop:/rainloop/data
ports:
  - 80:8888

```

#### How to setup

https://github.com/hardware/mailserver/wiki/Rainloop-initial-configuration
