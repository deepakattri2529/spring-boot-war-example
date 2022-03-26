pipeline {
    agent any
     tools {
        maven 'maven'
     }
    stages {
        stage('test') {
            steps {
              sh "mvn test"
            }
        }
        stage('build') {
            steps {
              sh "mvn package"
            }
        } 
		stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'b5b86e20-39a9-4102-b894-254fb46e8b4a', path: '', url: 'http://3.111.187.159:8080')], contextPath: '/app', war: '**/*.war'
            }
        }
    }
}
