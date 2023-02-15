pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/Natureboy100/jenkins-final-project.git'
            }
        }

        stage('build') {
            steps {
                echo "files 1"
                sh 'Python ./Python1/files 1.py'
            }
        }

        stage('build2') {
            steps {
                echo 'files 2'
                sh 'Python ./Python1/files 2.py'
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
