// pipeline {
//     agent any
//     tools{
//         maven 'maven'
//     }
//     stages{
//         stage('Build Maven'){
//             steps{
//                 checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/BREILYN1/node1_copia.git']]])
//                 sh 'mvn "-Dmaven.test.failure.ignore=true" "clean package"'
//             }
//         }
//         stage('Build image'){
//             steps{
//                 script{
//                     sh 'docker build -t 1023830656/musica_img1   .'
//                 }
//             }
//         }
//         stage('tag image'){
//             steps{
//                 script{
//                     sh 'docker tag musica_img1 1023830656/musica_img1' 
//                 }
//             }
//         }
//         stage('push image'){
//             steps{
//                 script{
//                     sh 'docker push 1023830656/musica_img1 ' 
//                 }
//             }
//         }
//     }
// }
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
//                  git([url: 'https://github.com/BREILYN1/node1_copia.git', branch: 'main'])
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
pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
// pipeline {
//     agent any
//     tools { 
//         maven 'maven' 
//         jdk 'jdk' 
//     }
//     stages {
//         stage ('Initialize') {
//             steps {
//                 sh '''
//                     echo "PATH = ${PATH}"
//                     echo "M2_HOME = ${M2_HOME}"
//                 ''' 
//             }
//         }
//         stage ('Build') {
//             steps {
//                 echo 'This is a minimal pipeline.'
//             }
//         }
//     }
// }

