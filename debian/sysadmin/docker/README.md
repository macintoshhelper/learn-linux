# Docker

## Getting Started
To install Docker:
```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
apt-get install -y software-properties-common
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
apt-get install -y apt-transport-https
apt-get update
apt-get install -y docker-ce
```

Use `systemctl status docker` to verify that the Docker service is running.


# Compile and run a Docker image

docker build -t <image-name> ./
docker run --name <container-name> -p 8080:8080 -d <image-name>

Where -p exposes the port outside of the container's local network to the system's network
