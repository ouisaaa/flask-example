node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("uhweng/d208backend")
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
