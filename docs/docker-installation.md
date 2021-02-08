# Setting up Docker and Docker Compose (Ubuntu 16.04 and 18.04.1)

## Docker installation on Ubuntu 16.04 LTS

```sh
sudo apt-get install curl
```

### Add repository key to package manager

Add Docker-Ubuntu's repository key to APT's trusted package sources:

```sh
curl --fail --silent --show-error --location https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### Install manager for software repositories

```sh
sudo apt-get install software-properties-common

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

sudo apt-get update
```

### Check availability of the docker-ce package

It should be available from previously installed Docker-repository:

```sh
apt-cache policy docker-ce
```

Should output something similar to:

```sh
docker-ce:

   Installed: (none)
...
```

### Install the docker-ce package

```sh
sudo apt-get install -y docker-ce
```

### Check Docker is running

```sh
sudo systemctl status docker
```

### Add your user to the docker group

```sh
sudo usermod -aG docker ${USER}
```

Take the new group in use with: `su - ${USER}`

## Docker compose installation

```sh
sudo curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

### Check Docker compose is installed

```sh
docker-compose --version
```

## Docker installation on Ubuntu 18.04.1 LTS

```sh
sudo apt install curl (if missing)
```

### Add repository key to package manager

Add Docker-Ubuntu's repository key to APT's trusted package sources:

```sh
curl --fail --silent --show-error --location https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### Install manager for software repositories

```sh
sudo apt install software-properties-common (if missing)

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

sudo apt update
```

### Check availability of the docker-ce package

It should be available from previously installed Docker-repository:

```sh
apt-cache policy docker-ce
```

Should output something similar to:

```sh
docker-ce:
   Installed: (none)
...
```

### Install the docker-ce package

```sh
sudo apt install -y docker-ce
```

### Check Docker is running

```sh
sudo systemctl status docker
```

### Add your user to the docker group

```sh
sudo usermod -aG docker ${USER}
```

Take the new group in use with: `su - ${USER}`

## Docker compose installation

```sh
curl -L https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m) -o ~/docker-compose

sudo mv ~/docker-compose /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

### Check Docker compose is installed

```sh
docker-compose --version
```

Should ouput something similar to:

```sh
docker-compose version 1.18.0, build 8dd22a9
```
