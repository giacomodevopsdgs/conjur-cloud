pipeline {
  agent any
  stages {
    stage('Test Conjur secret') {
      steps {
        withCredentials([string(credentialsId: 'CONJUR_SECRET', variable: 'CONJUR_VAL')]) {
          sh '''
            echo "Conjur secret fetched. Length: ${#CONJUR_VAL}"
            test -n "$CONJUR_VAL"
          '''
        }
      }
    }
  }
}
