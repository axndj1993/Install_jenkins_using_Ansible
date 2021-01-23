pipeline{
    agent any
    stages{  
        stage("Execute Ansible"){
            steps{
                ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'dev.inv', playbook: 'site.yml'
                echo "success"
            }
        }
    }
}
