pipeline {

      agent 
           {
            label 'ROBOSHOP'
       }
       environment {
            COURSE = "jenkins"
       }
       options {
              disableConcurrentBuilds()
       }
         stages {
            stage('Build') {
                steps {
                     script {
                         sh """
                                 echo "BUILDING"
                                 echo $COURSE
                         """
                     }
                }
            }
            stage('Test') {
                steps {
                    script {
                         sh """
                                 echo "Testing"
                         """
                     }
                }
            }
            stage('Deploy') {
                steps {
                     script {
                         sh """
                                 echo "Deploying"
                         """
                     }
                }
            }
         }
    post {
        always {
            echo 'Pipeline completed'
        }
        success {
             echo 'pipeline succeeded'
        }
        failure {
                echo 'pipeline failed'
        }
    }
}