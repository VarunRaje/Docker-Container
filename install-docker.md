To install Docker on Ubuntu, you can follow these steps to add the official Docker repository and install the necessary packages: Update System Packages.

```
sudo apt update
sudo apt upgrade -y
```
Install Prerequisites.

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```

Add Docker's GPG Key.

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

Add Docker Repository.

```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Install Docker Engine

```
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

Verify Installation.

```
sudo systemctl status docker
```

This command should show that the Docker service is active and running.
Run Docker without sudo (Optional but Recommended):
To avoid using sudo for every Docker command, add your user to the docker group:

```
sudo usermod -aG docker $USER
```

You will need to log out and log back in for this change to take effect. Test Docker Installation.

```
docker run hello-world
```
