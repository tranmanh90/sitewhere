#!/usr/bin/env groovy

node {

    stage('checkout') {
        checkout scm
    }

    stage('check java') {
        sh "java -version"
    }
	
	stage('export environment'){
		sh "export DOCKER_HOST=unix:///var/run/docker.sock"
	}

    stage('packaging') {
		echo "DOCKER_HOST is: $DOCKER_HOST"
        sh "./gradlew --project-prop debug clean dockerImage"
    }
}
