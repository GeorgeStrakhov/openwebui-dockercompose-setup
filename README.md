# set up private chatgpt interface for friends and family

1. Get a bare ubuntu droplet on Digital Ocean or anywhere else

2. Update everything and install Docker and Docker-compose

```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

# Install Docker Compose
sudo apt install docker-compose-plugin
```

3. Create a directory

```bash
mkdir openwebui

cd openwebui
```

4. Create an env file.
use .env.example

5. Create a traefik subdir and put in acme.json and make it 600

```bash
mkdir -p traefik
touch traefik/acme.json
chmod 600 traefik/acme.json
```

Also don't forget to put traefik.yml from this repo in there as well
Change your email there!!!


6. Put in docker-compose.yml inside openwebui dir. Change things if you need to

7. let's go

```bash
docker network create web

docker compose up -d
```

8. Go to the url and set up openwebui in the interface
