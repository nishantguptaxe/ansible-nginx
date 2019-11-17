This project deploys nginx on ec2 instances using private key

Jenkinsfile is being created to continuously integrated with CI/CD pipeline

Create a secret variable vault_password in jenkinsfile where password is stored to decrypt the file

export it into a file at the run time and pass it to decrypt the key

Finally run ansible playbook to deploy nginx on the desired instances 
