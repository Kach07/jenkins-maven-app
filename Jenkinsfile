pipeline {
  
    agent any
    
    tools{
       maven "Maven-3.9.6"
      // ansibile
   }

    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        
        stage('Create Image'){
            steps {
                installation: 'ansible'
                script {
                		sh 'ansible-playbook task.yml'
                	}
                }
            }
        
    


        // stage('Run Ansible Playbook') {
        //             steps {
        //                     ansiblePlaybook(
        //                     playbook: 'task.yml',
        //                     installation: 'ansible'
        //                 )
        //             }
        //         }
    }
}