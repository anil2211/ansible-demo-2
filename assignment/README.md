Pre-requisite Install ansible,boto3,amazon-galaxy collection,ansible-vault
openssl rand -base64 2048 > vault.pass
ansible-vault create secrets.yml --vault-password-file valut.pass
ansible-playbook ec2-create.yml --vault-password-file vault.pass
ansible-vault ec2-create.yml --ask-vault-password
ssh-copy-id -f "-o IdentityFile demo.pem" ubuntu@ipv4
eval "$(ssh agent -s)"
ssh-add pathofpem
ssh-add -l
ssh-keygen -y -f pathOfpem > pathOfpubPem.pub
ensure that 22 port is enable in ec2 instance
ssh ipv4