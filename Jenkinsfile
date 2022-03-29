<<<<<<< HEAD
pipeline {
  agent any
    stages {
        stage('Build') {
            steps {
                echo "building image"
            }
        }

        stage('test') {
            steps{
                echo "testing app"
            }
        }

        stage('Deploy') {
            steps{
                echo "Deploying the app"
            }
        }
    }
 }

=======
def gv

pipeline {
    agent any
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                    echo "building jar"
                    //gv.buildJar()
                }
            }
        }
        stage("build image") {
            steps {
                script {
                    echo "building image"
                    //gv.buildImage()
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    //gv.deployApp()
                }
            }
        }
    }   
}
>>>>>>> master
