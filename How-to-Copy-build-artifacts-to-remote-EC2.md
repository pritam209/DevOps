# How to Copy build artifacts to remote EC2

- Step 1: Generate new authentication key pairs for SSH 

- Step 2: Verify you are able to connect to remote vm using your current vm

- Step 3: Configure Jenkins to Connect to Remote Computer

- Step 4: Create new job in Jenkins - [ In this e.g. using pipeline project]

- Step 5: Follow this demo pipeline script

```bash
pipeline {
agent any

    environment {
        PRODUCTION_SERVER_1 = 'ubuntu@ip_address'
        PRODUCTION_SERVER_2 = 'ubuntu@ip_address'
        SSH_CREDENTIALS_ID = 'production-instance'  
    }
    
    # used to load nodejs during build
    tools {
        nodejs 'NodeJS'  
    }

    stages {
        stage('Cloning the App'){
            steps {
                script {
                    if (fileExists('.git')) {
                        sh 'git pull origin main'
                    } else {
                        sh 'git clone repo_url .'
                    }
                }
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Creating Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Copy build artifacts to remote EC2') {
            steps {
                sshagent(credentials: [env.SSH_CREDENTIALS_ID]) {
                    sh '''
                    scp -o StrictHostKeyChecking=no -r build/ ${PRODUCTION_SERVER_1}:/home/ubuntu/
                    scp -o StrictHostKeyChecking=no -r build/ ${PRODUCTION_SERVER_2}:/home/ubuntu/
                    exit
                    '''
                }
            }
        }
    }
    
}
```