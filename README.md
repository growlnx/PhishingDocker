# Phishing Docker

A simple docker-compose to be used in phishing simulations (red teaming).

## Getting Started

### You can begin by cloning this repository

```{sh}
git clone https://github.com/growlnx/PhishingDocker
```

### Update your SSL cert

You need update your SSL cert path inside **docker-compose.yml** file

> If you don't have a SSL Certificate yet, check this nice [tutorial](https://certbot.eff.org/docs/using.html#standalone)

```{sh}

```

### Update your domain

You need update your domain inside **nginx.conf** file

```{sh}

```

### Then you can start the services

```{sh}
cd PhishingDocker/src && docker-compose up -d
```

### Get your temporary gophish password

```{sh}
docker logs gophish 2>&1 | grep '[0-9a-z]{16}'
```
### Access your gophish dashboard using SSH local fowarding

```{sh}
ssh <USER>@<HOST> -L 8080:localhost:8080 -N
xdg-open http://localhost:8080
```
