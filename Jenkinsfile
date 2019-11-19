pipeline {
    agent any
    
      stage('Checkout external proj') {
        steps {
            git branch: 'master',
                credentialsId: 'my_cred_id',
                url: 'https://github.com/nishantguptaxe/ansible-nginx.git'
        }
    }

    stages {
        stage('Decrypt pem file and Deploy nginx') {
            steps {
                echo $vault_password > vault_key
                ansible-vault decrypt ./nishant_encrypted.pem --vault-password-file=./vault_key
                ansible-playbook -i inventory.cfg nginx.yml --private-key=./nishant_encrypted.pem 
            }
        }
    }
}
