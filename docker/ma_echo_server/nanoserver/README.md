# Docker image with ma_echo_server example on Windows Nano Server

## Assumptions

1. All commands use Bash syntax
1. Current directory is directory where this repository is cloned
1. [Docker](https://docs.microsoft.com/en-us/virtualization/windowscontainers/deploy-containers/deploy-containers-on-server) runs on [Windows Server 2016 1607 10.0.14393](https://docs.microsoft.com/en-us/windows-server/get-started/windows-server-release-info)
1. Docker 17.06+

## Building image

```bash
docker build -t abrarov/tcp-echo:latest-win docker/ma_echo_server/nanoserver
```

## Using image

Run ma_echo_server:

```bash
docker run -d --name echo -p 9:9999 abrarov/tcp-echo:latest-win --port 9999 --inactivity-timeout 300
```

Get help about supported parameters:

```bash
docker run --rm abrarov/tcp-echo:latest-win --help
```
