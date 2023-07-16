pipeline {
    agent any

    stages {
        stage('Buzz Buzz') {
            steps {
                echo "the devs are ${BUZZ_NAME}!"
                archive
                
            }
        }
        stage('Buzz Buzz 2') {
            steps {
                sh 'echo the devs are buzzin! 2!>test.txt'
            }
        }

    }
    environment {
        BUZZ_NAME = 'Worker Bee'
    }
}
