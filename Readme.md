Ansible commands can be executed in Control node

Masternodes can be autorized to control by using password less authentication permenently--this can be done in 3 ways
   1.using sshkeygen -- copying privatekey of controlnode to authorization key on manage noes
   2.using ssh ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
   3.using password .. ssh-copy-id ec2-user@publicip ( for doing this password login must be enabled on manage node)


  For simple executions you can use Adhoc commands
...........................................................................

 for creating executing playbooks

    ansible-playbooks -i inventory.ini playbook-name

  ...............................................................

  for creating roles

     ansible-galaxy role init rolename
............................................................
for using any ansible files from galaxy

   example
    ansible-galaxy role install bsmeding.docker

   --------- Ansible_Collections------------------------------
   use ansible galaxy for doenloading any collections

   for aws - ansible-galaxy collection install amazon.aws

   prerequests - pip install boto3

   we need to setup vault integration for the aws creaditials

   for vault password 

    openssl rand -base64 2048 > vault.pass

  for craeting vault

    ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass

   to see the contents in vault 

   ansible-vault view group_vars/all/pass.yml --vault-password-file vault.pass

   executing ansible collection playbook with vault set up

    ansible-playbook playbbokname --vault-password-file vault.pass

