pipeline {
    agent any

    stages {
        stage('version') {
            steps {
                sh 'python3 --version || sudo apt-get update && sudo apt-get install -y python3'
            }
        }
        stage('clone') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/Natureboy100/jenkins-final-project.git'
            }
        }
        stage('build') {
            steps {
                echo "files 1"
                sh 'python3 ./Python 1/files 1.py'
            }
        }

        stage('build2') {
            steps {
                echo 'files 2'
                sh 'python3 ./Python 2/files 2.py'
            }
        }

        stage('test') {
            steps {
                echo 'security testing'
                snykSecurity(snykInstallation: 'snyk', snykTokenId: 'synk-api-token', additionalArguments: '--all-projects')
            }
        }
    }
}
