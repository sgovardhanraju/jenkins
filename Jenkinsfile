pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        COURSE = "jenkins"
    }
    options {
      timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

        stages {
            stage ('Build') {
                steps {
                    script {
                        sh """
                            echo "Building"
                            echo $COURSE
                           sleep 10
                           env
                        """
                    }
                }
            }
            stage ('Test'){
                steps {
                    script {
                        sh """
                            echo "Testing"
                            echo $COURSE
                        """
                    }
                }
            }
            stage ('Deploy'){
                steps {
                    script {
                        sh """
                            echo "Deploying"
                            echo $COURSE
                        """
                    }
             }
        }
    }
    post {
        always {
            echo "I will always say Hello Again!!"
            cleanWs()
        }
        success {
            echo "I will run if Success"
        }
        failure {
            echo "I will stop if Failure"
        }
        aborted {
            echo "pipeline is aborted"
        }
    }
}