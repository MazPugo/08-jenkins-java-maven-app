#!/usr/bin/env groovy

@Library('jenkins-shared-library') 
pipeline {
    agent any
    tools {
        maven 'Maven'
    }

    stages {
        stage("build jar") {
            steps {
                script {
                    buildJar()
                }
            }
        }

        stage("build image") {
            steps {
                script {
                    buildImage()
                }
            }
        }

        stage("deploy") {
            steps {
                script {
                    deployApp()
                }
            }
        }
    }
}

jenkins-shared-library
