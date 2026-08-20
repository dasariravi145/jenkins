pipeline {

      agent {
            node {

                  label 'ROBOSHOP' 
            }
      }
      stages {

            stage('Build') {

                  steps {
                        echo 'Building the Project'
                        exit 1
                  }
            }
            stage('install') {
               steps{
                      echo 'Installing the Project'
                   }
            }
            stage('test'){
                    steps{
                        echo 'Testing the Project'
                        sh 'exit 0'
                    }
            }

      }
      post {
            always { 
            echo 'I will always say Hello again!'
        }
        success {
            echo "pipeline success"
        }
        failure {
            echo "pipeline failure"
        }
      }
}