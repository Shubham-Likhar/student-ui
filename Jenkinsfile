pipeline {
    agent any
    stages {
        stage("git-checkout"){
            steps {
               sh 'sudo apt-get update -y'
               sh 'sudo apt-get install git -y'
               git 'https://github.com/Shubham-Likhar/student-ui.git' 
            }
        }
        stage("build-mvn"){
            steps {
                sh 'sudo apt-get update -y'
                sh 'sudo apt-get install maven unzip curl -y'
                sh 'mvn clean package'
            }
        }
        
          stage("push-artifact"){
            steps {
                sh '''
                curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
                unzip awscliv2.zip  
                sudo ./aws/install
                '''
                sh '''                
                aws s3 cp /var/lib/jenkins/workspace/pipeline1/target/studentapp-2.2-SNAPSHOT.war s3://dev-artifact-upload/
                '''
            }
        }
       
        
    }
}
