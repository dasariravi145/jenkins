pipeline {

      agent any
      stages {

            stage('Build') {

                  steps {
                        echo 'Building the Project'
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
                        exit
                    }
            }

      }
      post {
            always {

                    echo 'cleanup and build completed'
            }
            failure {
                    echo 'Build failed'
            }
      }
}