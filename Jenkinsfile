pipeline {
    agent any

    stages {
        stage('Clean') {
            steps {
                bat 'mvn clean'
            }
        }
        stage('Package to .jar') {
            steps {
                bat 'mvn install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                bat 'cd target && java -jar demo-0.0.1-SNAPSHOT.jar' //Try archive 'target*//*.jar'
            }
        }
    }
    post{
        always{
            echo "Done with everything! Deployed on localhost:9090"
            //mail bcc: '', body: 'Yo Dawg!', cc: '', from: '', replyTo: '', subject: 'Test Mail Jenkins #01', to: 'mstale20@gmail.com'
        }
    }
}
