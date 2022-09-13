
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
          sh "ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null -q prashanthg@172.29.181.114 'cd /home/prashanthg/DockerProjects/My_notes && sudo docker build -t projecttest-img .'"
        }  
      }
    }
    stage('Launching Container'){
      steps{
        sshagent(['101']){
          sh "ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null -q prashanthg@172.29.181.114 'sudo docker run -d --name nginx_v1.0 --privileged=true -v /etc/hosts:/etc/hosts -p 999:80 projecttest-img:latest /usr/sbin/init'"
        }
      }
    }
  }

}
