pipeline {
    agent any

    tools {
        python "python3"
        nodejs "node"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Natureboy100/jenkins-final-project.git'
            }
        }

        stage('Build 1') {
            steps {
                echo 'Running files1.py'
                sh 'python3 ./Python 1/files 1.py'
            }
        }

        stage('Build 2') {
            steps {
                echo 'Running files2.py'
                sh 'python3 ./Python 2/files 2.py'
            }
        }

        stage('Security Test') {
            steps {
                echo 'Running security testing'
                snykSecurity additionalArguments: '--all-projects', snykInstallation: 'snyk', snykTokenId: 'snyk-api-token'
            }
        }
    }
}
