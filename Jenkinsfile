#!/usr/bin/env groovy

node {

    stage('checkout') {
        checkout scm
    }

    stage('check java') {
        sh "java -version"
    }

    stage('packaging') {
        sh "export DOCKER_HOST=unix:///var/run/docker.sock\n./gradlew --project-prop debug clean dockerImage"
    }
	
	stage('deploy'){
		sh "export DOCKER_COMPOSE=/home/viniot/deployment/platform\ndocker-compose up -d"
	}
}
