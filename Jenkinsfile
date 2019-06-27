#!/usr/bin/env groovy

node {
    agent any
    environment {
        DOCKER_HOST='unix:///var/run/docker.sock'
    }

    stage('checkout') {
        checkout scm
    }

    stage('check java') {
        sh "java -version"
    }

    stage('packaging') {
        sh "./gradlew --project-prop debug clean dockerImage"
    }
}
