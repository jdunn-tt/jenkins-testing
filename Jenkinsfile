library 'shared-pipeline-comms'

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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