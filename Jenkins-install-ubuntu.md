# How to install Jenkins 

## This guide will provide you step by step instruction how to install jenkins on ubuntu

1. Install Java

```bash
sudo apt update
```

```bash
sudo apt install fontconfig openjdk-17-jre
```

```bash
java -version
```

2. Install Jenkins

```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```

```bash
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install jenkins
```

3. start,stop,enable,status
```bash
sudo systemctl start jenkins
sudo systemctl stop jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins
```

Note: Make sure to enable inbound rules in security - PORT 8080

