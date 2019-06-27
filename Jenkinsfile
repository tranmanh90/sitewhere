#!/usr/bin/env groovy

node {
	agent { label 'docker' }
    environment {
		DOCKER_HOST="unix:///var/run/docker.sock"
    }

    stage('checkout') {
        checkout scm
    }

    stage('check java') {
        sh "java -version"
    }

    stage('packaging') {
		echo "DOCKER_HOST is: $DOCKER_HOST"
        sh "./gradlew --project-prop debug clean dockerImage"
    }
}
