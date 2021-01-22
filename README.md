# myapp-ansible

```
pipeline{
    agent any
    stages{
        stage("checkout"){
            steps{
                git 'https://github.com/axndj1993/myapp-ansible.git'
                echo 'success'
            }
        }
        
        stage("Execute Ansible"){
            steps{
                ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'dev.inv', playbook: 'site.yml'
            }
        }
    }
}
```
