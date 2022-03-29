pipeline {
  agent any
    stages {
        stage('Build') {
            steps {
                sh echo "building image"
            }
        }
        
        stage('test') {
            steps{
                sh echo "testing app"
            }         
        }
        
        stage('Deploy') {
            steps{
                sh echo "Deploying the app"
            }
        }
    }
 }
