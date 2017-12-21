pipeline {
    agent {
        docker { image 'ubuntu:14.04' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'pwd'
                sh 'ls /tmp'
                sh 'ls ~'
            }
        }
    }
}
