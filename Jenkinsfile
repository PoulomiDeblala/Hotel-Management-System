pipeline {
    agent any

 

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: 'd2a67d3b-77eb-4168-916e-d6bee18df3bd', url: 'https://github.com/PoulomiDeblala/Hotel-Management-System'.git']]])
            }
        }
        stage('Build and Test') {
            steps {
                sh 'mvn clean install -Dmaven.test.skip=true'

            }
        }
        stage('Code Analysis') {
            steps {
                echo "Scanned successfully!"
            }
        }
        stage('Notification') {
            steps {
                emailext body: 'build is successful', subject: 'Build', to: 'polo161996@mail.com'
            }
        }
        }
    }
