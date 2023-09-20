#!/usr/bin/env groovy
pipeline {
    agent any
        stages {
            stage('Stopping') {
                steps {
                    sh 'Stopping Vetlog'
                    sh 'ssh josdem@vetlog.org "/home/josdem/deploys/stop-vetlog.sh"'
                    echo 'Done!'
                }
            }
            stage('Removing') {
                steps {
                    echo 'Removing Vetlog'
                    sh 'ssh josdem@jmailer.josdem.io "/home/josdem/deploys/remove-vetlog.sh"'
                    echo 'Done!'
                }
            }
            stage ('Building') {
                steps {
                    echo 'Starting Build Job'
                    echo 'Call remote build job'
                    echo 'Done!'
                }
            }
        }
}