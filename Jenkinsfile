pipeline {

    agent any

    tools { 
        maven 'maven3' 
    }

    options {
        buildDiscarder logRotator( 
                    daysToKeepStr: '15', 
                    numToKeepStr: '10'
            )
    }

    environment {
        APP_NAME = "DCUBE_APP"
    }

    stages {
        
        

        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/master']], 
                    userRemoteConfigs: [[url: 'https://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@github.com/relesseAston/hello.git']]
                ])
            }
        }

        stage('Code Build') {
            steps {
                 bat 'mvn install'
            }
        }

    }   
}
