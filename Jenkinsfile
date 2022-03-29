pipeline {
  agent any
    stages {
        stage('test') {
            steps{
                echo "testing app"
                sh 'mvn test'
            }
        }
        stage('Build') {
            steps {
                echo "building image"
                sh 'mvn clean package'
                sh 'docker build -t java-maven-app:3.0 .'

            }
        }

        stage('Publish') {
            steps{
                echo "Pushing the app"
                sh 'aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 580534504601.dkr.ecr.us-east-2.amazonaws.com'
                sh 'docker tag java-maven-app:3.0 580534504601.dkr.ecr.us-east-2.amazonaws.com/java-maven-app:3.0'
                sh 'docker push 580534504601.dkr.ecr.us-east-2.amazonaws.com/java-maven-app:3.0'
            }
        }
    }
 }
