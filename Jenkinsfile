pipeline {
     environment {
        BB_AUTHOR_INFO = 'NA'
        PATH = "$PATH:/usr/local/bin"
     }
     agent any
     
     stages {

          stage('Swift Lint'){
            steps{
                   println "Swift lint..."
                   swiftLint() 
                  
            }
          }
     }
}
def swiftLint(){
  FAILED_AT_STAGE = 'Swift Lint'
         withEnv(["HOME=${env.WORKSPACE}"]) {
            sh "swiftlint --config .swiftlint.yml"
            sh "swiftlint lint --reporter html > swiftlint.html"
         }
}
