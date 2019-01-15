library 'shared-pipeline-comms', 'jenkins-shared-build'

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                dockerBuild.defineImage('java:8u144-jdk')
                dockerBuild.prepImage()
                dockerBuild.pushImage()
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