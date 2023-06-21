pipeline {
    agent any
    tools {nodejs "NodeJS"}

    stages {
        stage('Run automated tests') {
            steps {
                echo 'Run automated tests'
                sh 'npm install'
                sh 'npm install cypress'
                sh 'npm install xvfb'
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
                    echo("timeout")
                }
            }
        }
    }
}
