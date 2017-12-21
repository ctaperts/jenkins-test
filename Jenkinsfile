/*
Test pipeline RedRoomApi
*/

currentBuild.result = "SUCCESS"
pipeline {
  agent {
    docker {
      image 'colbyt/dotnet-ubuntu'
      args '-v $HOME/jenkins/build-dotnet:/app/build-dotnet -v $HOME/.ssh:/root/.ssh'
    }
  }
  stages {
    stage('Test') {
      steps {
        echo 'Test'
      }
    }
    stage('Build') {
      steps {
        echo 'Build'
        sh 'touch /app/build-dotnet/build-${BUILD_NUMBER}'
        // sh 'cd RedRoomAPI'
        // sh 'dotnet restore'
        // sh 'dotnet publish -c Release -o RedRoomAPI'
        // sh 'tar czf /app/build-dotnet/RedRoomApi-${BUILD_NUMBER}.tar.gz RedRoomAPI'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy'
        // sh 'cp /app/build-dotnet/RedRoomAPI-${BUILD_NUMBER}.tar.gz /app/build-dotnet/RedRoomAPI2-${BUILD_NUMBER}.tar.gz'
        echo 'ssh to web server and deploy'
        // sh '#ssh deploy@xxxxx.xxxxx.com running/xxxxxxx/dockerRun.sh'
      }
    }
    stage('email-sucess') {
      steps {
        mail body: 'project build successful',
                    from: 'admin@redroomnola.com',
                    replyTo: 'admin@redroomnola.com',
                    subject: 'project build successful',
                    to: 'colby.taperts@gmail.com'
      }
    }
  }
}
