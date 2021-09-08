pipeline{
   agent any
   //triggers { 
     // pollSCM('* * * * *')
      //}
   stages{
         stage('Verify Branch'){
            steps{
               echo "$GIT_BRANCH"
            }
         }
         stage('Test'){
            steps{
              pwsh 'docker --version'
            }
         }
   }
}