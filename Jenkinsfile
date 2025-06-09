pipeline {
    agent any
    tools {
        maven 'Maven' // Replace with your desired Maven version
         // Replace with your desired JDK version
    }
    stages {
        stage('Checkout') {
            steps {
                git branch : 'master' ,url :'https://github.com/R-Navyashree/MyApp.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Run Application') {
            steps {
                
                sh 'java -jar target/MyApp-1.0-SNAPSHOT.jar'
            }
        }
    }
    post{
    	success{
    		echo 'Build and Depolyment Successfull'
    	}
    	failure{
    		echo 'Build failed!
    		}
    	}
}
