#!/usr/bin/env groovy
pipeline {
    agent any
        stages {
            stage('Build') {
                steps {
                    sh 'Stopping Vetlog'
                    sh 'ssh josdem@vetlog.org "/home/josdem/deploys/stop-vetlog.sh"'
                    echo 'Done!'
                }
            }
        }
}