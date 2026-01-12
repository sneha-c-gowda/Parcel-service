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
        sudo apt update
        sudo apt install -y maven
        export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))
        echo $JAVA_HOME
        export PATH=$JAVA_HOME/bin:$PATH
        echo $PATH
        '''
      }
    }
  }
}
  
