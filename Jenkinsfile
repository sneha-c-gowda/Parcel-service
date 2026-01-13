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
        export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))
        export PATH=$JAVA_HOME/bin:$PATH
        '''
      }
    }
      stage ("deploy") {
      steps {
        sh '''
       mvn clean package
       mvn spring-boot:run
        '''
      }
    }
  }
}
  
