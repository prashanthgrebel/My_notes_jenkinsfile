
pipeline {
  agent any
  
  stages{
    stage('cloning files from git repo') {
      steps{
        sshagent(['101']) {
          sh "ssh -o StrictHostKeyChecking=no prashanthg@172.29.87.227 ' ls -lrth'"
        } 
        
      }
    }
  
  }

}
