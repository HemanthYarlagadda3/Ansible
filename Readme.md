Ansible commands can be executed in Control node

Masternodes can be autorized to control by using password less authentication permenently--this can be done in 3 ways
   1.using sshkeygen -- copying privatekey of controlnode to authorization key on manage noes
   2.using ssh ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
   3.using password .. ssh-copy-id ec2-user@publicip ( for doing this password login must be enabled on manage node)


  For simple executions you can use Adhoc commands
