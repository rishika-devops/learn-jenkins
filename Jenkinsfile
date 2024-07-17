pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        GREETING = "hello jenkins"
    }
    options {
        timeout(time: 1 , unit : 'SECONDS')
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
                sh """
                  echo "here i wrote shell scrpit"
                  echo "$GREETING"
                  sleep 10
                """  
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


