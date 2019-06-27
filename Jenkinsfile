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
        sh "cd /home/viniot/deployment/platform && docker-compose up -d"
    }
}
