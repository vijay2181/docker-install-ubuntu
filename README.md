# docker-install-on-ubuntu-and-amzln

```
# Install Latest Docker
 curl -fsSL https://get.docker.com -o get-docker.sh
 sudo sh get-docker.sh
```

ubuntu@ip-172-31-23-222:~$ docker --version

Docker version 20.10.21, build 20.10.21-0ubuntu1~22.04.3

```
sudo systemctl enable docker 
sudo systemctl start docker
```

ubuntu@ip-172-31-23-222:~$ docker ps

Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json": dial unix /var/run/docker.sock: connect: permission denied

```
sudo usermod -aG docker <current_username>
sudo usermod -aG docker ubuntu
```

still if you do **docker ps** you will get permission error, so you need to refreh the terminal or exit from terminal and login back

Note that the changes will take effect the next time the user logs in or opens a new terminal session.

To reflect the group membership changes in the same terminal session.run below commands

```
sudo usermod -aG docker ubuntu
newgrp docker
```

```
# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

ubuntu@ip-172-31-23-222:~$ docker-compose --version

docker-compose version 1.29.2, build 5becea4c

