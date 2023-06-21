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
                echo 'SQ'
            }
        }
        stage('JMeter test') {
            steps {
                echo 'JMETER'
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
