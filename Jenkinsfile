pipeline {
  agent any
  tools {
    maven 'Maven:3.8'
  }
  parameters {
    choice(name: 'VERSION', choices: ['2.0', '3.0', '4.0'], description: '')
    booleanParam(name: 'executeTests', defaultValue: true , description: '')
    
  }
    stages {
        stage('test') {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                echo "testing app"
                sh 'mvn test'
            }
        }
        stage('Build') {
            steps {
                echo "building image"
                sh 'mvn clean package'
                sh 'docker build -t java-maven-app:4.0 .'

            }
        }

        stage('Publish') {
            steps {
                echo "Pushing the version ${params.VERSION}"
                sh 'aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 580534504601.dkr.ecr.us-east-2.amazonaws.com'
                sh 'docker tag java-maven-app:4.0 580534504601.dkr.ecr.us-east-2.amazonaws.com/java-maven-app:4.0'
                sh 'docker push 580534504601.dkr.ecr.us-east-2.amazonaws.com/java-maven-app:4.0'
            }
        }
    }
 }
