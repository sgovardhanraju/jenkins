pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    stages {
        stage('Build') { 
            steps {
                echo "building" 
            }
        }
        stage('Test') { 
            steps {
                echo "testing"
            }
        }
        stage('Deploy') { 
            steps {
                echo "deploying"
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