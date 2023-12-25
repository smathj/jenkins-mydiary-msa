node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', 
        url: 'https://github.com/smathj/jenkins-mydiary-msa.git',
        brach: 'main'
    }

    stage('Build image') {
       dockerImage = docker.build("smathj/mydiary-front:2.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}

