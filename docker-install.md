### docker install in ubuntu

```sh
# Uninstall old packages in machine
sudo apt-get remove docker docker-engine docker.io containerd runc

# Update the apt package index and install packages to allow apt to use a repository over HTTPS:
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

# Add docker's GPG key of aliyun mirrors:
curl -fsSL https://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
# or ustc mirrors:
curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -

# Set up the stable repository of aliyun, the mirrors addr should be consistent with upper key
# Note: arch=amd64/arm64 should be consistent with machine arch
sudo add-apt-repository "deb [arch=amd64] https://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
# or repository of ustc:
sudo add-apt-repository  "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu  $(lsb_release -cs) stable" 

# Update the apt package index
sudo apt-get update

# If you want to install specific version of Docker Engine, list the versions available in your repo
apt-cache madison docker-ce

# list like below:
docker-ce | 5:18.09.2~3-0~ubuntu-bionic | http://xxx/docker-ce/linux/ubuntu bionic/stable amd64 Packages
docker-ce | 5:18.09.1~3-0~ubuntu-bionic | http://xxx/docker-ce/linux/ubuntu bionic/stable amd64 Packages
docker-ce | 5:18.09.0~3-0~ubuntu-bionic | http://xxx/docker-ce/linux/ubuntu bionic/stable amd64 Packages
docker-ce | 18.06.3~ce~3-0~ubuntu | http://xxx/docker-ce/linux/ubuntu bionic/stable amd64 Packages
docker-ce | 18.06.2~ce~3-0~ubuntu | http://xxx/docker-ce/linux/ubuntu bionic/stable amd64 Packages

# Install Docker Engine and containerd
sudo apt-get install docker-ce=5:19.03.8~3-0~ubuntu-bionic docker-ce-cli=5:19.03.8~3-0~ubuntu-bionic containerd.io
```


#### docker install in debian

```shell
# Uninstall old packages in machine
sudo apt-get remove docker docker-engine docker.io containerd runc

# Update the apt package index and install packages to allow apt to use a repository over HTTPS:
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

# Add docker's GPG key of aliyun mirrors:
curl -fsSL https://mirrors.aliyun.com/docker-ce/linux/debian/gpg | sudo apt-key add -
# or ustc mirrors:
curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/debian/gpg | sudo apt-key add -

# Set up the stable repository of aliyun, the mirrors addr should be consistent with upper key
# Note: arch=amd64/arm64 should be consistent with machine arch
sudo add-apt-repository "deb [arch=amd64] https://mirrors.aliyun.com/docker-ce/linux/debian $(lsb_release -cs) stable"
# or repository of ustc:
sudo add-apt-repository  "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/debian  $(lsb_release -cs) stable" 

# Update the apt package index
sudo apt-get update

# If you want to install specific version of Docker Engine, list the versions available in your repo
apt-cache madison docker-ce

# list like below:
docker-ce | 5:18.09.2~3-0~debian-stretch | http://xxx/docker-ce/linux/debian stretch/stable amd64 Packages
docker-ce | 5:18.09.1~3-0~debian-stretch | http://xxx/docker-ce/linux/debian stretch/stable amd64 Packages
docker-ce | 5:18.09.0~3-0~debian-stretch | http://xxx/docker-ce/linux/debian stretch/stable amd64 Packages
docker-ce | 18.06.3~ce~3-0~debian | http://xxx/docker-ce/linux/debian stretch/stable amd64 Packages
docker-ce | 18.06.2~ce~3-0~debian | http://xxx/docker-ce/linux/debian stretch/stable amd64 Packages

# Install Docker Engine and containerd
sudo apt-get install docker-ce=5:19.03.8~3-0~debian-stretch docker-ce-cli=5:19.03.8~3-0~debian-stretch containerd.io
```
