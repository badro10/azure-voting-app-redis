pipeline {
   agent any

   stages {
      stage('Vérify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            sh 'docker images -a'
            sh '''
              cd azure-vote
              docker build -t jenkins-pipeline .
              docker images -a
              cd ..
            '''
         }
      }
   }
}
