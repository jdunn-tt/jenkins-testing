@Library('jenkins-shared-comms') comms
@Library('jenkins-shared-build') build

pipeline {
    agent {label 'github01'}

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                //dockerBuild()
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy to Dev') {
            steps {
                echo 'Deploying....'
            }
        }

        stage('Integration Test') {
            steps {
                test()
                script {
                    test.testFunction()
                }
            }
        }

        stage ('Slack') {
            steps {
                slackNotify(true)
            }
        }

        stage('Email') {
            steps {
                emailNotify()
            }
        }
    }
}