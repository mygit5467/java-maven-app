pipeline {
    agent any

    tools {
        maven 'Maven3.9.9'
    }

    stages {

        stage('Clone') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }


	stage('Package') {
    	steps {
        echo 'Packaging the application...'
        sh 'mvn clean package'
    		}
	}

	tage('Deploy') {
            steps {
                echo 'Deploying the application (simulated)...'
                sh 'java -jar target/java-maven-app-1.0-SNAPSHOT.jar'
            }
        }

        stage('Run') {
            steps {
                echo 'Packaging application...'
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'java -jar target/*.jar'
            }
        }

    }
}
