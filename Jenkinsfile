node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("unn-project/yskimdev1031")
         
     }
     stage('Push image') {
         docker.withRegistry('https://ec2-3-34-45-91.ap-northeast-2.compute.amazonaws.com/', 'harbor-reg') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
