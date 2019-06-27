#!/usr/bin/env groovy

node {

    environment {
		DOCKER_HOST=unix:///var/run/docker.sock
    }

    stage('checkout') {
        checkout scm
    }

    stage('check java') {
        sh "java -version"
    }
	
	stage('export'){
		sh '${DOCKER_HOST}'
	}

    stage('packaging') {
        sh "./gradlew --project-prop debug clean dockerImage"
    }
}
