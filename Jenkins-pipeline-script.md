# Jenkins Pipeline Project Script

```bash
pipeline {
    agent any
    
    # used to load Node.js 
    # Install Nodejs plugin
    # Configure it Jenkins -> tools
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
        stage('Start Server') {
            steps {
                sh 'pm2 start index.js'
            }
        }
    }

    post {
        success {
            mail to: 'youremail@gmail.com',
            subject: "Enter Subject Here",
            body: "Enter Body Here"
        }
        failure {
            mail to: 'youremail@gmail.com',
            subject: "Enter Subject Here",
            body: "Enter Body Here"
        }
    }
}
```