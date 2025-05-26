pipeline {
    agent any

    tools{
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
                echo 'Running Maven Build...'
                sh 'mvn clean compile'
            }
        }

        stage('Run') {
            steps {
                echo 'Executing Java App...'
                sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
            }
        }
    }
}
