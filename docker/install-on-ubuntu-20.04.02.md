# Install Docker on Ubuntu 20.04.02 LTS

### Notes
- Installing from default Ubuntu repos, not Docker offical.

### Steps
- `sudo apt update`
- `sudo apt-get remove docker docker-engine docker.io`
- `sudo apt install docker.io`
- `docker --version` (displays 20.10.7)
- `sudo systemctl start docker`
- `sudo systemctl enable docker` (enable run at startup)
- Reboot and check Docker status again to confirm run at startup works
- `sudo groupadd docker` make sure 'docker' group exists
- `sudo usermod -aG docker ubuntu` Put user `ubuntu` in `docker` group
- Logout then login again
- `id -nG` make sure logged in user is in `docker` group
- `docker info` should work now without sudo
- `docker run hello-world` to make sure things are working


