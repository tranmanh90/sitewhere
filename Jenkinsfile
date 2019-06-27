#!/usr/bin/env groovy

node {

    stage('checkout') {
        checkout scm
    }

    stage('check java') {
        sh "java -version"
    }

    stage('packaging') {
        sh "sudo export DOCKER_HOST=unix:///var/run/docker.sock\n./gradlew --project-prop debug clean dockerImage"
    }
}
