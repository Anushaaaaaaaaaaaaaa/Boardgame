pipeline {
    agent any
    
    tools {
        maven 'maven3.6'
        jdk 'jdk'
    }

    // environment {
    //     SCANNER_HOME = tool 'sonar-scanner'
    // }

    stages {
        
        stage('Checkout') {
            steps {
             git 'https://github.com/Anushaaaaaaaaaaaaaa/Boardgame.git'
            }
        }
        
        stage('Compile') {
            steps {
            //    sh 'mvn package'
            }
        }

        stage('Test') {
            steps {
            //    withSonarQubeEnv('sonar-server') {
            //         sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Boardgame -  Dsonar.projectKey=Boardgame \
            //               -Dsonar.java.binaries=target/classes '''
            }
        }

        stage('Build') {
            steps {
                // script {
                //     withDockerRegistry(credentialsId: 'dockerhub-cred', toolName: 'docker') {
                //         sh "docker build -t boardwebapp:latest ."
                //         sh "docker tag boardwebapp:latest anushaanayak/boardwebapp:latest"
                //     }
                // }  
            }
        }
        stage('Deploy') {
            steps {
               
            }
        }

    }
}
