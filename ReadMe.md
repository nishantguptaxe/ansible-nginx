This project deploys nginx on ec2 instances using private key

Jenkinsfile is being created to continuously integrated with CI/CD pipeline

Create a secret variable vault_password in jenkinsfile where password is stored to decrypt the file

my_cred_id is the credential id which needs to be created in jenkins which contains the credential details to connect to the git repo

export it into a file at the run time and pass it to decrypt the key

Finally run ansible playbook to deploy nginx on the desired instances 

ansible-playbook -i inventory.cfg nginx.yml --private-key=./nishant_encrypted.pem
