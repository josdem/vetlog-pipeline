#!/usr/bin/env groovy
pipeline {
    agent any
        stages {
            stage('Stopping') {
                steps {
                    echo 'Stopping Vetlog'
                    sh 'ssh josdem@vetlog.org "/home/josdem/deploys/stop-vetlog.sh"'
                    echo 'Done!'
                }
            }
            stage('Removing') {
                steps {
                    echo 'Removing Vetlog'
                    sh 'ssh josdem@vetlog.org "/home/josdem/deploys/remove-vetlog.sh"'
                    echo 'Done!'
                }
            }
            stage ('Building') {
                steps {
                    echo 'Starting Build Job'
                    build job: 'vetlog'
                    echo 'Done!'
                }
            }
            stage ('Moving') {
                steps {
                    echo 'Moving Vetlog'
                    sh 'ssh josdem@vetlog.org "/home/josdem/deploys/move-vetlog.sh"'
                    echo 'Done!'
                }
            }
            stage ('Starting') {
                steps {
                    echo 'Start Vetlog'
                    sh 'ssh josdem@vetlog.org "/home/josdem/deploys/start-vetlog.sh"'
                    echo 'Done!'
                }
            }
        }
}