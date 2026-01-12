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
  }
}
  
