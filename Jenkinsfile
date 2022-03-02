node{
    stage("SCM Checkout"){
        git 'https://github.com/samkhan95/aegis_front.git'
    }
    stage("Build the image"){
        sh 'sudo docker build -t samad095/aegis_front .'
    }
    stage("Pushing the image on Docker Hub"){
        withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
            sh "sudo docker login -u samad095 -p ${dockerHubPwd}"
        }
        sh 'sudo docker push samad095/aegis_front'
    }
    
    
}
