pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    stages {
        stage('Build') { 
            steps {
                echo 'building'
            }
        }
        stage('Test') { 
            steps {
                echo 'testing'
            }
        }
        stage('Deploy') { 
            steps {
                echo 'deploying'
            }
        }
    }
    post {
        always {
            echo " i will always say hello again"
        }
        failure {
            echo " this runs when pipeline is failed , used generally to send some alerts"
        }
        success {
            echo " i will say hello when pipeline is success"
        }
    }
}


