def gv

pipeline {
    agent any
    tools {
        maven 'maven-3.9'
    }
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }

        stage("build jar") {
            steps {
                script {
                    echo "building the application..."
                    sh 'mvn package'
                }
            }
        }

        stage("build image") {
            steps {
                script {
                    echo "building the docker image..."
                    sh 'docker build -t mazpugo/demo-app:jma-2.0 .'
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                        sh 'echo $PASS | docker login -u $USER --password-stdin'
                        sh 'docker push mazpugo/demo-app:jma-2.0'
                    }
                }
            }
        }

        stage('deploy') {
            steps {
                script {
                    echo "Deploying..."
                }
            }
        }
    }
}
