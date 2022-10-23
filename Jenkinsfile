pipeline {
    agent any
    stages {
        stage('Code') {
            steps {
               sh 'git clone --branch features https://github.com/Sravia94/docker-sravia'
            }
        }
        stage('Build') {
            steps {
                sh 'step2.sh'
            }
        }
       
    }
}
