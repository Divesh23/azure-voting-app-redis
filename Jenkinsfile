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
               docker --version
              pwsh(script:'docker images -a')
              pwsh(script:"""
                  docker --version
                  """)
               /*pwsh(script:"""
                  cd azure-vote/
                  docker images -a
                  docker images -t jenkins-pipeline .
                  docker images -a
                  cd..
               """)*/
               
            }
         }
   }
}