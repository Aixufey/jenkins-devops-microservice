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

    // Specific agent machine
    // agent { docker { image 'maven:3.9.9-amazoncorretto-17-al2023'} }

    // ConfigureTools from Jenkins automatic installers
    // This option allows to use any agent machine and use the tools installed in Jenkins by listing their names
    environment {
        dockerHome = tool 'myDocker'
        mavenHome = tool 'myMaven'
        PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
    }

    stages {
        stage('Checkout') {
            steps {
                sh "mvn --version"
                sh "docker version"
                echo "Build"
                echo "PATH - $PATH"
                echo "BUILD_NUMBER - $env.BUILD_NUMBER"
                echo "BUILD_ID - $env.BUILD_ID"
                echo "JOB_NAME - $env.JOB_NAME"
                echo "BUILD_TAG - $env.BUILD_TAG"
                echo "BUILD_URL - $env.BUILD_URL"
            }
        }

        stage('Compile') {
            steps {
                sh "mvn clean compile"
            }
        }

        stage('Test') {
            steps {
                sh "mvn test"
            }
        }
        
        stage('Integration Test') {
            steps {
                sh "mvn failsafe:integration-test failsafe:verify"
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
