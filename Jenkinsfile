pipeline {
    agent any
    stages{
        stage('Build Maven'){
            stages{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/BREILYN1/node1_copia.git']]])
                echo 'mvn -Dmaven.test.failure.ignore=true clean package'            
            }
        }
    }
}