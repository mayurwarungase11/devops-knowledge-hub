# SonarQube Installation Using Docker

## Prerequisites

* Docker installed
* Port 9000 open in Security Group (for EC2)

## Pull and Run SonarQube

```bash
docker run -itd --name SonarQube-Server -p 9000:9000 sonarqube:lts-community
```

## Verify Container Status

```bash
docker ps
```

## Check Container Logs

```bash
docker logs SonarQube-Server
```

## Access SonarQube

```text
http://<EC2-Public-IP>:9000
```

## Default Credentials

```text
Username: admin
Password: admin
```

## Stop SonarQube

```bash
docker stop SonarQube-Server
```

## Start SonarQube

```bash
docker start SonarQube-Server
```

## Remove SonarQube

```bash
docker rm -f SonarQube-Server
```
