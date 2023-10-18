@Library('my-jenkins-library') _
nexusSharedLibrary.groovy
pipeline {
    agent any
    stages {
        stage('npm package') {
            steps {
                script {
                    echo 'Running npm package'
                    nexusSharedLibrary.npm_package()
                }
            }
        }

        stage('docker build') {
            steps {
                script {
                    echo 'Building Docker image'
                    docker_build()
                }
            }
        }

        stage('container deploy') {
            steps {
                script {
                    echo 'Deploying container'
                    container_deploy()
                }
            }
        }

        stage('push image to Nexus') {
            steps {
                script {
                    echo 'Pushing Docker image to Nexus'
                    push_image()
                }
            }
        }
    }
}
