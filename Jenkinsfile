pipeline {
    agent any
    stages {
        stage('Code') {
            steps {
               sh 'rm -rf docker-sravia'
               sh 'git clone --branch features https://github.com/Sravia94/docker-sravia'
               sh 'cd docker-sravia' 
            }
        }
        stage('Build') {
            steps {
                sh 'apt-get update'
                sh 'aapt install -y curl jq'
                sh 'curl https://get.docker.com | sudo bash'
                sh 'version=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | jq -r '.tag_name')'
                sh 'curl -L "https://github.com/docker/compose/releases/download/${version}/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose'
                sh 'chmod +x /usr/local/bin/docker-compose'
                sh 'docker-compose up -d'
            }
        }
        
       
    }
}
