pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '10e29c98-029e-467b-9002-9c7288a60abe', path: '', url: 'http://54.242.18.56:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
