pipeline {
        agent none
        

    stages {
        stage('Buzz Buzz') {
            agent {
                label 'master'
            }
            steps {
                echo "the devs are ${BUZZ_NAME}!"
                
            }
        }
        stage('Buzz Buzz 2') {
            
            agent {
                label 'node1'
            }
            steps {
                sh 'echo the devs are buzzin! 2!>tet.txt'
                archiveArtifacts(artifacts: '*.txt', fingerprint: true)
                stash(name: 'test')
            }
        }
        stage('Parallel Test') {
            parallel {
                stage('Statge P1') {
                    agent {
                        label 'master'
                    }
                    steps { 
                        unstash 'test'
                        sh 'cat tet.txt'
                        sh 'echo par1'
                        input(message: 'Archive?', ok: 'Yes')
                        archiveArtifacts(artifacts: '*.txt', fingerprint: true)
                    }
                }
                stage('Statge P2') {
                    agent {
                        label 'master'
                    }
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


