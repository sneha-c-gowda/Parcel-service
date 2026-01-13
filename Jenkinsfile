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
       set -e
      mvn clean install
      timeout 300 mvn spring-boot:run || echo "Spring Boot stopped after 5 minutes"
        '''
      }
    }
  }
}
  
