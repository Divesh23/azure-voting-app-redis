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
         }
         stage('Docker Build'){
            steps{
               pwsh(script:'docker images -a')
               pwsh(script:"""
                  docker images -a
                  docker images -t jenkins-pipeline .
                  docker images -a
                  cd..
               """)
            }
         }
   }
}