pipeline {
    agent any

    stages {
        stage('Buzz Buzz') {
            steps {
                echo "the devs are ${BUZZ_NAME}!"
                
            }
        }
        stage('Buzz Buzz 2') {
            steps {
                sh 'echo the devs are buzzin! 2!>test.txt'
                archiveArtifacts(artifacts: '*.txt', fingerprint: true)
            }
        }
        stage('Parallel Test') {
            parallel {
                stage('Statge P1') {
                    steps {
                        sh 'echo par1'
                        archiveArtifacts(artifacts: '*.txt', fingerprint: true)
                    }
                }
                stage('Statge P2') {
                    steps {
                        sh 'echo par2'
                    }
                }

            }
        }

    }
    environment {
        BUZZ_NAME = 'Worker Bee'
    }
}


