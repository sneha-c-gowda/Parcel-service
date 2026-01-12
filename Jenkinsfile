pipeline {
  agent any 

  stages {
    stage ("checkout") {
      steps {
        sh '''
        rm -rf Parcel-service
        git clone https://github.com/sneha-c-gowda/Parcel-service.git
        '''
      }
    }
      stage ("build") {
      steps {
        sh '''
        cd Parcel-service
        git branch feature-1
        git branch
        '''
      }
    }
      stage ("deploy") {
      steps {
        sh '''
        sudo apt install -y openjdk-11-jdk
        export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))
        export PATH=$JAVA_HOME/bin:$PATH
        mvn clean install
        nohup java -jar target/*.jar > app.log 2>&1 &
        '''
      }
    }
  }
}
  
