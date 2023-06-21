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
                script {
                      scannerHome = tool 'sonar-scanner';
                }
            withSonarQubeEnv('cypress-google-search') { 
                sh "${scannerHome}/bin/sonar-scanner"
            }
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
