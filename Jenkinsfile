pipeline {
    agent any

    stages {
        stage('Run automated tests') {
            steps {
                echo 'Run automated tests'
            }
        }
        stage('SonarQube analysis') {
            steps {
                
            }
        }
        stage('JMeter test') {
            steps {
                
            }
        }
        stage('Perform manual testing') {
            steps {
                echo 'Perform manual testing'
                timeout(activity: true, time: 2880) {
                    input 'Proceed to production?'
                }
            }
        }
    }
}
