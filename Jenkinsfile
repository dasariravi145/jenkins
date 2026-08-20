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
            timeout(time: 5, unit:  'SECONDS') 
      }
      parameters {
        string(name: 'PERSON', defaultValue: 'Mr Ravi', description: 'Who should I say hello to?')  

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'DEPLOYE', defaultValue: false, description: 'Deployee this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                        sh """
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "DEPLOYE: ${params.DEPLOYE}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
                        """
                    }
            }
            stage('deployee'){
                  when {
                        expression { return params.DEPLOYE }
                  }
                    steps{
                        sh """
                            echo "Deployee the Project"
                        """
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