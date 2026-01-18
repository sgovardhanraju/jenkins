pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        COURSE = "jenkins"
    }
        stages {
            stage ('Build') {
                steps {
                    script {
                        sh """
                            echo "Building"
                            echo $COURSE
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
    }
}