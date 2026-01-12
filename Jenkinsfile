pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
        environment {
            COURSE = "Jenkins"
        }
    stages {
        stage('Build') { 
            steps {
                script {
                    sh """
                        echo "building" 
                        echo $COURSE
                        env
                        """
                }
            }
        }
        stage('Test') { 
            steps {
                script {
                    sh """
                        echo "testing" 
                        echo $COURSE
                        """
                }
            }
        }
        stage('Deploy') { 
            steps {
                script {
                    sh """
                        echo "deploying" 
                        echo $COURSE
                        """
                }
            }
        }
    }
    post {
        always {
            echo " I will always say Hello again!"
            cleanWs()
        }
        success {
            echo "I will run if Sucess"
        }
        failure {
            echo "I will run if Failure"
        }
    }
}