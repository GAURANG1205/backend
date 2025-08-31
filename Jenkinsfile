pipeline {
   agent any

   triggers {
      githubPush()
   }
        stages{
            stage('Clone the Backend Repo'){
                steps{
                   git 'https://github.com/GAURANG1205/backend'
               }
             }
             stage('Build jar'){
                 steps{
                   sh 'mvn clean package -DskipTests'
                 }
             }
             stage('Run the Docker Compose'){
                 steps{
                   sh 'docker-compose down || true'
                   sh 'docker-compose up -d --build'
                   }
             }
        }
   post{
       success{
        echo 'Deploy Successfullysada dsa'
       }
       failure{
       echo 'Failure Unable to ddeployed'
       }
   }
}