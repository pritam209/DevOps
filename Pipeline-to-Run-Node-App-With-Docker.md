# This guide will walk you through Jenkins pipeline demo, how to run node app with Docker.

```bash
pipeline {
    agent any
    tools {
        nodejs 'NodeJS' 
    }

    stages {
        stage('Cloning the App') {
            steps {
                script {
                    if (fileExists('.git')) {
                        sh 'git pull origin main'
                    } else {
                        sh 'git clone repo-url .'
                    }
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t nodejs-with-docker .'
                }
            }
        }
        stage('Stop Previous Container') {
            steps {
                script {
                    sh '''
                    if [ $(docker ps -q -f name=nodejs-with-docker) ]; then
                        docker stop nodejs-with-docker
                        docker rm nodejs-with-docker
                    fi
                    '''
                }
            }
        }
        stage('Run Docker Image') {
            steps {
                script {
                    sh 'docker run -d --name nodejs-with-docker -p 9000:3000 nodejs-with-docker'
                }
            }
        }
    }
}
```

# Note: Ensure Jenkins user has permission to run Docker without sudo

To ensure that the Jenkins user has permission to run Docker commands without using sudo, you need to add the Jenkins user to the docker group. This allows the Jenkins user to run Docker commands as a non-root user.

Here are the steps to do this:

- Step 1: Create the Docker group (if it doesn't already exist)

```bash
sudo groupadd docker
```

- Step 2: Add the Jenkins user to the Docker group

```bash
sudo usermod -aG docker jenkins
```

- Step 3: Restart the Jenkins service and log out/in:

```bash
sudo systemctl restart jenkins
```

- Step 4: Verify the Jenkins user is in the Docker group:

```bash
groups jenkins
```