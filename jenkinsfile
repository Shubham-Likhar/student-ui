pipeline {
    
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
        
       
        
    }
}
