pipeline {

    agent 
    {
       node {

            label 'ROBOSHOP'
       }
        
    }

    environment {
        COURSE = "jenkins"
    }

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'SECONDS')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {

        stage('Build') {
            steps {
                sh """
                    echo "BUILDING"
                    echo "${COURSE}"
                """
            }
        }

        stage('Test') {
            steps {
                sh """
                    echo "Testing"
                    echo "Hello ${params.PERSON}"
                    echo "Biography: ${params.BIOGRAPHY}"
                    echo "Deploy: ${params.DEPLOY}"
                    echo "Choice: ${params.CHOICE}"
                    echo "Password: ${params.PASSWORD}"
                """
            }
        }

        stage('Deploy') {
            when {
                expression {
                     params.DEPLOY
              }
            }
            steps {
                sh """
                    echo "Deploying"
                """
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'Pipeline succeeded'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}