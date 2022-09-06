pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/BREILYN1/node1_copia.git']]])
                echo 'mvn -Dmaven.test.failure.ignore=true clean package'
            }
        }
        stage('Build image'){
            steps{
                script{
                    echo 'docker build -t 1023830656/musica_img1 .'
                }
            }
        }
        stage('tag image'){
            steps{
                script{
                    echo 'docker tag musica_img1 1023830656/musica_img1' 
                }
            }
        }
        stage('push image'){
            steps{
                script{
                    echo 'docker push 1023830656/musica_img1 ' 
                }
            }
        }
    }
}
