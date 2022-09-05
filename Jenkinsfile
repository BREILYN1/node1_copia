pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/BREILYN1/node1_copia.git']]])
                sh 'mvn -Dmaven.test.failure.ignore=true clean package'
            }
        }
        stage('Build image'){
            steps{
                script{
                    sh 'docker build -t 1023830656/musica_img1 .'
                }
            }
        }
        stage('tag image'){
            steps{
                script{
                    sh 'docker tag musica_img1 1023830656/musica_img1' 
                }
            }
        }
        stage('push image'){
            steps{
                script{
                    sh 'docker push 1023830656/musica_img1 ' 
                }
            }
        }
    }
}