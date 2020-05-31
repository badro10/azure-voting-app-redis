pipeline {
   agent {label 'docker'}

   stages {
      stage('Vérify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
       }
      stage('Push to registry') {
         steps {
           echo "workspace is $workspace"
             dir ("$workspace/azure-vote") {
               script {
                 docker.withRegistry('https://index.docker.io/v1/', 'DockerHub') {
                 def myImage = docker.build("bfennane/test-app:1.0.0")
                 myImage.push()
                 }
               }
             }
         }
      }
      stage ('Test Using Trivy') {
        steps {
          sh 'pwd'
          sh 'trivy bfennane/test-app:1.0.0'
        }
      }
   }
}
