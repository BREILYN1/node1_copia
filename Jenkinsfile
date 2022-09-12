pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/BREILYN1/node1_copia.git']]])
                shell 'mvn -Dmaven.test.failure.ignore=true clean package'
            }
        }
        stage('Build image'){
            steps{
                script{
                    shell 'docker build -t 1023830656/musica_img1 .'
                }
            }
        }
        stage('tag image'){
            steps{
                script{
                    shell 'docker tag musica_img1 1023830656/musica_img1' 
                }
            }
        }
        stage('push image'){
            steps{
                script{
                    shell 'docker push 1023830656/musica_img1 ' 
                }
            }
        }
    }
}
// pipeline {
//     agent any
//     stages{
//         stage('verify tooling'){
//             steps {
//                 script {
//                     shell    ''''
//                         shell  'echo $USER  '
//                         shell 'docker version'  
//                     '''
//                 }
//             }
//         }
//         stage ( 'checkout' ) {
//             steps{
//                 // git branches: 'main',
//                 // url 'https://github.com/BREILYN1/node1_copia.git'
//                 shell 'pwd'
//                 shell 'ls -la'
//             }
//         }
//         stage ("prueba echo") {
//             steps{
//                 echo "hola"
//             }
//         }
//     }
// }
// pipeline {
//     agent {
//         docker { image 'node:14-alpine' }
//     }
//     stages {
//         stage('Test') {
//             steps {
//                 shell 'node --version'
//             }
//         }
//     }
// }



