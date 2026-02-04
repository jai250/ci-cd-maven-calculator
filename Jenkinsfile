pipeline {
	agent any
	stages {
		stage('Checkout') {
			steps {
				checkout([
					$class: 'GitSCM',
					branches: [[name: '*/main']],
					   userRemoteConfigs: [[
						   url: 'https://github.com/jai250/ci-cd-maven-calculator.git',
						   credentialsId: 'side'
					   ]]
				])
			}
		}

        stage('check') {
            steps {
                sh '''
                    pwd
                    ls -lrta
                '''
            }
        }        
	}
}
