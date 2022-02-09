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
                deploy adapters: [tomcat9(credentialsId: '21034379-1b0d-4efb-850f-6dbe6ed92c41', path: '', url: 'http://13.232.59.12:8080/')], contextPath: '/app2', war: '**/*.war'
            }
        }
    }
}
