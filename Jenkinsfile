pipeline {
    agent any

    stages {
        stage('Run automated tests') {
            steps {
                echo 'Run automated tests'
                sh npm install cypress
            }
        }
        stage('SonarQube analysis') {
            
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
