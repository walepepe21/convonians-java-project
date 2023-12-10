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
                deploy adapters: [tomcat9(credentialsId: 'tompass', path: '', url: 'http://100.26.111.243:8080/')], contextPath: 'myapp', war: '**/*.war', war: '**/*.war'
            }
        }
    }
}
