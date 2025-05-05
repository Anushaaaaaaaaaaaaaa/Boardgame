pipeline {

    // agent any

    agent {
        label 'slavenode1'
    } 
    
    tools {
        maven 'maven3.6'
        jdk 'jdk17'
    }

    environment {
        SCANNER_HOME = tool 'sonar-scanner'
    }

    stages {
        
        stage('Checkout') {
            steps {
             git branch: 'main', url: 'https://github.com/Anushaaaaaaaaaaaaaa/Boardgame.git'
            }
        }
        
        stage('Compile') {
            steps {
               sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
               withSonarQubeEnv('sonar-server') {
                // sh 'mvn sonar:sonar' // or whatever your scanner command is
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Boardgame -Dsonar.projectKey=Boardgame \
                          -Dsonar.java.binaries=target/classes '''
                }
            }
        }

        // stage('Docker Build Image') {
        //     steps {
        //         script {
        //             withDockerRegistry(credentialsId: 'dockerhub-credentials', toolName: 'docker') {
        //                 sh "docker build -t boardwebapp:latest ."
        //                 sh "docker tag boardwebapp:latest anushaanayak/boardwebapp:latest"
        //             }
        //         }

        //     }
        // }

        // stage('Docker Push Image') {
        //     steps {
        //         script {
        //             withDockerRegistry(credentialsId: 'dockerhub-credentials', toolName: 'docker') {
        //                 sh "docker push anushaanayak/boardwebapp:latest"
        //             }
        //         }
                
        //     }
        // }


    }
}
