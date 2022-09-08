
pipeline {
  agent any
  
  stages{
    stage('Removing old file and Git CheckOut') {
      steps{
        sshagent(['101']) {
          sh ""
          sh "ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null -q prashanthg@172.29.181.114 'rm -rf /home/prashanthg/DockerProjects/* && cd /home/prashanthg/DockerProjects/ && git clone https://github.com/prashanthgrebel/My_notes.git'"
        }
      }
    }
    stage('Building Docker image'){
      steps{
        sshagent(['101']) {
         sh "ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null -q prashanthg@172.29.181.114 'cd /home/prashanthg/DockerProjects/My_notes && sudo docker buil -t projecttest-img .'"
        }  
      }
    
    }
  
  }

}
