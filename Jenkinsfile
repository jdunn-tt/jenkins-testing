@Library('shared-pipeline-comms') comms
@Library('jenkins-shared-build') build

pipeline {
    agent { label 'tests' }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                script {
                    dockerBuild.defineImage('java:8u144-jdk')
                    dockerBuild.prepImage()
                    dockerBuild.pushImage()
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }

        stage('Tester') {
            steps {
                test()
            }
        }

        stage('Hipchat') {
            steps {
                hipchatNotify(false, 'JDjenkins')
            }
        }

        stage('Mattermost') {
            steps {
                mattermostNotify()
            }
        }

        stage('Email') {
            steps {
                emailNotify()
            }
        }
    }
}