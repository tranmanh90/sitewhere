#!/usr/bin/env groovy

node {
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
