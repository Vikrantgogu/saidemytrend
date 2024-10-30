pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"

    }
    stages {

        stage ('Built') {
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage ('Sonar Qube Analisys') {
            environment {
                scannerHome = tool 'vikrant-sonar-scan'
            }
            steps {

                withSonarQubeEnv('vikrant-sonar-scan') {
                   sh "${scannerHome}/bin/sonar-scanner"
                    
                }

            }
        }


    }
}

