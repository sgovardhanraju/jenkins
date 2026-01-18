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
        timeout(time: 10, unit: 'SECONDS')
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