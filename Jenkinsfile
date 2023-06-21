pipeline {
    agent any
    tools {nodejs "NodeJS"}

    stages {
        stage('Run automated tests') {
            steps {
                echo 'Run automated tests'
                //sh 'npm install'
                //sh 'npm install cypress'
                //sh 'npm run cypress:open'
                //sh 'npm run cypress:run'
            }
        }
        stage('SonarQube analysis') {
            steps{
                echo 'SONAR'
                script {
                      scannerHome = tool 'sonar-scanner';
                }
                withSonarQubeEnv('sonar-scanner') { 
                    sh "${scannerHome}/bin/sonar-scanner"
                    sh '"sonar.projectKey=sq_pe2" -D"sonar.sources=." -D"sonar.host.url=https://sonar.creis.pt" -D"sonar.login=9307044250e7060ecab2339f5649fd7b5ab052e7"'
                }
                //sh 'sonar-scanner.bat -D"sonar.projectKey=sq_pe2" -D"sonar.sources=." -D"sonar.host.url=https://sonar.creis.pt" -D"sonar.login=9307044250e7060ecab2339f5649fd7b5ab052e7"'
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
