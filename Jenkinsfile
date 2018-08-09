pipeline {
    agent any

    stages {
        stage('validate') {
            steps {
		git 'https://github.com/vijaymargam/mvn-webapp.git'
                sh 'mvn validate'
		echo 'Building..'
            }
        }

        stage('Test') {
            steps {
		git 'https://github.com/vijaymargam/mvn-webapp.git'
		sh 'mvn test'
                echo 'Testing..'
            }
        }

	stage(package) {
	steps {
		git 'https://github.com/vijaymargam/mvn-webapp.git'
		sh 'mvn package'
		echo 'building application..'
		}
	}

	stage(tomcat deployment) {
	steps{
		git 'https://github.com/vijaymargam/mvn-webapp.git'
		sh 'mvn tomcat7:deploy'
		echo 'deploying application to tomcat application server'
			}
	}


        stage('Deploy') {
            steps {
		git 'https://github.com/vijaymargam/mvn-webapp.git'
		sh 'mvn deploy'
                echo 'Deploying to nexus repositories..'
            }
        }

    }
}
