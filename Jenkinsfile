pipeline {
  agent any
  stages {
    stage('Test Conjur secret') {
      steps {
        withCredentials([
          conjurSecretCredential(credentialsId: 'CONJUR_SECRET', variable: 'TEST_SECRET')
        ]) {
          sh '''
            set +x
            [ -n "$TEST_SECRET" ] || { echo "Conjur secret is empty"; exit 1; }
            echo "Secret length: ${TEST_SECRET}"
          '''
        }
      }
    }
  }
}

// pipeline {
//   agent any
//   stages {
//     stage('Show identity') {
//       steps {
//         echo "jenkins_full_name = ${env.JOB_NAME}"
//       }
//     }
//   }
// }
