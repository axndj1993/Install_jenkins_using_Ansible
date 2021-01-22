# Jenkins job to install jenkins on an EC2 instance using Ansible

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

Watch this youtube video as a referene to create credentials and also how to use pipeline syntax
https://www.youtube.com/watch?v=PRpEbFZi7nI
