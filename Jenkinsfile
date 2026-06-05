pipeline {

      agent 
           {
            label 'ROBOSHOP'
       }
         stages {
            stage('Build') {
                steps {
                     script {
                         sh """
                                 echo "BUILDING"
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