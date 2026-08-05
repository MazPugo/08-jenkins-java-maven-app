#!/usr/bin/env groovy

@Library('jenkins-shared-library') _
def gv

pipeline {
    agent any
    tools {
        maven 'Maven'
    }

    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }

        stage("test") {
            steps {
                script {
                    echo "Testing the application..."
                    echo "Executing pipeline for branch ${env.BRANCH_NAME}"
                }
            }
        }

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
                    gv.deployApp()
                }
            }
        }
    }
}