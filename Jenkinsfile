pipeline {
    agent any

    tools {
        maven 'M3'
    }

    environment {
        SONAR_SCANNER_HOME = tool 'SonarScanner'
    }

    stages {

        stage('Build & Test') {
            steps {
                sh 'mvn clean test'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                    mvn sonar:sonar \
                    -Dsonar.projectKey=maven-calculator \
                    -Dsonar.projectName="Maven Calculator"
                    '''
                }
            }
        }
    }
}
