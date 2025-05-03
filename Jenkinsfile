pipeline {

    agent {
        label 'slavenode1'
    } 
    
    tools {
        maven 'maven3.6'
        jdk 'jdk17'
    }

    // environment {
    //     SCANNER_HOME = tool 'sonar-scanner'
    // }

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

        // stage('Test') {
        //     steps {
        //        withSonarQubeEnv('sonar-server') {
        //             sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Boardgame -  Dsonar.projectKey=Boardgame \
        //                   -Dsonar.java.binaries=target/classes '''
        //     }
        // }

        // 
        
        // stage('Deploy') {
        //     steps {
               
        //     }
        // }

    }
}
