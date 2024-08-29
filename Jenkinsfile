// SCRIPTED PIPELINE
/*node {
	stage('Build') {
		echo "Build"
	}
	stage('Test') {
		echo "Test"
	}
	stage('Integration Test') {
	    echo "Integration Test"
	}
}*/

// DECLARATIVE PIPELINE
pipeline {
    // agent any
    agent { docker { image 'maven:3.9.9-amazoncorretto-17-al2023'} }
    stages {
        stage('Build') {
            steps {
                sh 'mvn --version'
                echo 'Build'
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Integration Test') {
            steps {
                echo 'Integration Test'
            }
        }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'Run on success'
        }
        failure {
            echo 'Run on failure'
        }
    }
}
