@Library('shared-pipeline-comms') _
@Library('jenkins-pipeline-build') _

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // script {
                //     dockerBuild.defineImage('java:8u144-jdk')
                //     dockerBuild.prepImage()
                //     dockerBuild.pushImage()
                // }
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