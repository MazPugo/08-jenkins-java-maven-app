pipeline {
    agent any
    stages {
        stage("test") {
            steps {
                script {
                    echo "Testing the application..."
                    echo "Executing pipeline for integration..."
                }
            }
        }
        stage("build") {
            when {
                expression {
                    env.GIT_BRANCH == "origin/main"
                }
            }
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }
        stage("deploy") {
            when {
                expression {
                    env.GIT_BRANCH == "origin/main"
                }
            }
            steps {
                script {
                    echo "Deploying the application..."
                }
            }
        }
    }
}
