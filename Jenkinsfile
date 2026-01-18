pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
        stages {
            stage ('Build') {
                steps {
                    echo "Building"
                }
            }
            stage ('Test'){
                steps {
                    echo "Testing"
                }
            }
            stage ('Deploy'){
                steps {
                    echo "Deploying"
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
    }
}