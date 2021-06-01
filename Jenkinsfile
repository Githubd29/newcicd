#!groovy
pipeline {
    agent any
    
      stages {
        stage('Build') {
            steps {
                git 'https://github.com/maheshwari2876/testjen.git'
                
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh 'echo "My first pipeline1"'
            }
        }
    }
}
