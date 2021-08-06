pipeline {
    agent any
    
    tools {
        go 'golang-1.15'
    }
    
    environment {
        GO111MODULE = 'off'
    }
    
    stages {
        stage('Golang Environment Check') {
            steps {
                //echo 'Hello World';
                //sh "ls -la";
                //sh "go version";
                //sh label: 'golang_version', returnStatus: true, script: 'go version'
                //tool name: 'golang-1.15', type: 'go'
                //def root = tool type: 'go', name: 'Go 1.15'
                //tool name: 'golang-1.15', type: 'go'
                
                /*
                withEnv(["GOROOT=${root}", "PATH+GO=${root}/bin"]) {
                  sh 'go version'
                }
                */
                sh 'go version';
                sh "echo ${GO111MODULE}";
            
            }
            

            
        }
         stage('Build') {
            steps {
                echo 'Building....'
            }
        }
         stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        
         stage('Test') {
            steps {
                echo 'Testing....'
            }
        }
        
         stage('Release') {
            steps {
                echo 'Reeasing....'
            }
            post {
               
                always {
                    //emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
                    mail to: "bill.rassel@gmail.com", subject:"${currentBuild.currentResult}: ${currentBuild.fullDisplayName}", body: "Test passed."
                }
            }
        }
        
        
    }
}
