pipeline {
   agent any

   stages {
      stage('Vérify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Goodbye') {
         steps {
            sh 'echo "Hello World !"'
         }
      }
   }
}
