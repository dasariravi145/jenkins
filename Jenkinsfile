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
}