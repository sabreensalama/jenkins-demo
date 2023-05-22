#!/usr/bin/env groovy
pipeline {
    agent any
    triggers {
         githubPush(
            name: 'main'
        )
    }

    
    stages {
        stage('Build App') {
            steps {
                script {
                    tags_extra = "value_1"
                }
               echo "Start Building the APP................................................"
               
            }
        }
        stage('Deploy App') {
            steps {
                echo "Start Deploying the APP................................................"
                 sshagent(['Bastion_key']) {
                        // Replace "remote-user" and "remote-host" with your own values
                        sh "ssh -o StrictHostKeyChecking=no ubuntu@10.0.0.11 'touch test'"
                    }
            }
        }
    }
}
