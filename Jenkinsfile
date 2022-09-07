
pipeline {
  agent any
  
  stages{
    stage('cloning files from git repo') {
      steps{
        sh "rm -rf .git"
       
        sh "git clone https://github.com/prashanthgrebel/My_notes.git"
      }
    }
  
  }

}
