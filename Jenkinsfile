#!/usr/bin/env groovy

node {

    dir ('/home/viniot/deployment/platform') {
        sh 'pwd'
    }

    stage('test'){
        sh "cd /home/viniot/deployment/platform"
    }

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
        sh "export DOCKER_COMPOSE=/home/viniot/deployment/platform\ncd $DOCKER_COMPOSE && docker-compose up -d"
    }
}
