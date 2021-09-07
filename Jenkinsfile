pipeline{
   agent any
   triggers { 
      pollSCM('* * * * *')
      }
   stages{
         stage('Verify Branch'){
      steps{
         echo "$GIT_BRANCH"
      }
         stage('Docker Build'){
            pwsh(script:'docker images -a');
            pwsh(script:"""
                  cd azure-vote/
                  docker images -a
                  docker images -t jenkins-pipeline .
                  docker images -a
                  cd..
            """)
         }
    }
   }
}