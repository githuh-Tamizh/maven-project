pipeline {
  environment {
    registry = "raji2306/jenkinsdockerimage"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
   tools {
        maven 'maven'
        jdk 'java'
    }
   stages{
       stage("GitHub Checkout Stage"){
           steps{
               git credentialsId:'Git-ssh', url: 'git@github.com:raji2306/java-hello-world-with-maven.git'
          }
        }
        stage("Maven Build Stage"){
            steps{
                sh 'mvn clean install'
            }
        }
//         stage("Deploy to Tomcat Server"){
//             steps{
//                 script{
//                     deploy adapters: [tomcat9(credentialsId:'Tomcat-user', path:'',url:'http://13.232.82.57:8080')],contextPath:'/pipeline', onFailure: false, war: '**/*.war'
//                }
//             }
//         }
//         stage("Running Ansible Playbook"){
//             steps{
//                 ansiblePlaybook credentialsId: 'ansible-play', disableHostKeyChecking: true, installation: 'ansible', inventory: 'host', playbook: '/etc/ansible/tomcat.yaml'
//             }    
//         }
//     stage('Building image') {
//       steps{
//         script {
//           dockerImage = docker.build registry + ":$BUILD_NUMBER"
//         }
//       }
//     }
//     stage('Deploy Image') {
//       steps{
//         script {
//           docker.withRegistry( '', registryCredential ) {
//             dockerImage.push()
//           }
//         }
//       }
//     }
//     stage('Running the container') {
//       steps{
//         sh "docker run -itd --name jenkinsdockercontainer -p 85:80 $registry:$BUILD_NUMBER"
//       }
//     }
//     stage('Remove Unused docker image') {
//       steps{
//         sh "docker rmi $registry:$BUILD_NUMBER"
//       }
//     }
  }
}
