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
    // agent { docker { image 'maven:3.9.9-amazoncorretto-17-al2023'} }
    stages {
        stage('Build') {
            steps {
                // sh 'mvn --version'
                echo 'Build'
                echo 'PATH - $PATH'
                echo 'BUILD_NUMBER - $env.BUILD_NUMBER'
                echo 'BUILD_ID - $env.BUILD_ID'
                echo 'JOB_NAME - $env.JOB_NAME'
                echo 'BUILD_TAG - $env.BUILD_TAG'
                echo 'BUILD_URL - $env.BUILD_URL'
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
