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
        timeout(time: 1 , unit : 'HOURS')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'mr.jenkins', description: 'How should I say hello?')
        string(name: 'BIOGRAPHY', defaultValue: '', description: 'enter some info about the person')
        string(name: 'TOGGLE', defaultValue: true, description: 'toggle this value')
        string(name: 'CHOICE', choices: ['One','Two','Three'], description: 'pick something')
        string(name: 'PASSWORD', defaultValue: 'secret', description: 'enter a password')

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
        stage('check params') { 
            steps {
                sh """
                  echo "hello ${params.PERSON}"
                  echo "biograpthy: ${params.BIOGRAPHY}"
                  echo "toggle: ${params.TOGGLE}"
                  echo "choice: ${params.CHOICE}"
                  echo "password: ${params.PASSWORD}"
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


