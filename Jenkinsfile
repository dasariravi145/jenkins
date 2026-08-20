pipeline {

      agent {
            node {

                  label 'ROBOSHOP' 
            }
      }
      environment {
               COURSE = "Jenkins"
      }
      options {
            disableConcurrentBuilds()
      }
      stages {

            stage('Build') {

                  steps {
                        sh """
                        echo 'Building the Project'
                        echo ${COURSE}
                        """
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