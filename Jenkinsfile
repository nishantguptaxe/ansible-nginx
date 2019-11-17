pipeline {
    agent any

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
