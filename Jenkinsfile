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
    agent any
    stages {
        stage('Build') {
            steps {
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
    } post {
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
