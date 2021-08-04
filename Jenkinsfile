pipeline {
    agent any
    stages {
        stage (' GIT Checkout' ){
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'gitaccess', url: 'https://github.com/vajohnvinodh/javaSpringBoot-master.git']]])
                }
            }
        }
        stage('Build Image') {
            steps {
                sh """
                docker build -t "springboot" .
                """
            }
        }
    }
}
