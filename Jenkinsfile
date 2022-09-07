
pipeline {
  agent any
  
  stages{
    stage('cloning files from git repo') {
      steps{
        sh "rm -rf /var/lib/jenkins/workspace/My_notes/*"
       
        sh "git clone https://github.com/prashanthgrebel/My_notes.git"
      }
    }
  
  }

}
