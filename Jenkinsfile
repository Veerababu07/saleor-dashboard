pipeline {
    agent { label 'openjdk-docker' }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/Veerababu07/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t veerababu07/saleor-dashboar:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push veerababu07/saleor-dashboar:DEV'
            }
        }
    }
}
