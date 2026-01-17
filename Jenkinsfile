pipeline {
  agent { label 'slave1' }

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
    stage ("publish") {
      steps {
        sh '''
      mvn clean install

        '''
      }
    }
    stage ("deploy") {
      steps {
        sh '''
       cd /var/lib/jenkins/workspace/Parcel_service_pipeline/target
       mvn spring-boot:run

        '''
      }
    }
  }
}
  
