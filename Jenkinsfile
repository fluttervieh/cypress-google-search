pipeline {
    agent any

    stages {
        stage('Run automated tests') {
            steps {
                echo 'Run automated tests'
                sh 'npm i'
                sh 'npm install cypress'
                sh 'npm run cypress:open'
                sh 'npm run cypress:run'
            }
        }
        stage('SonarQube analysis') {
            steps{
                echo 'SONAR'
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
