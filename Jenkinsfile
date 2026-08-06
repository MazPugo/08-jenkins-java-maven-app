@Library('jenkins-shared-library') _
pipeline {
    agent any
    tools {
        maven 'maven-3.9'
    }
    stages {
        stage("init") {
            steps {
                script {
                    def gv = load "script.groovy"
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
<<<<<<< HEAD
                    buildimage('mazpugo/demo-app:jma-3.0')
=======
                    buildimage()
>>>>>>> b5dfb509f41d9a780fe4a7dec24d6ba8e99b2a6f
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