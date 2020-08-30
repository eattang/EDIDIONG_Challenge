# Prerequisites
1. Ansible (Instructions available at https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
2. Install boto3 using `pip install boto3 --user`
3. `mkdir ~/.aws && touch ~/.aws/credentials`
4. Add the following at `~/.aws/credentials`
  > [default]\
  > aws_access_key_id = YOUR_AWS_ACCESS_KEY\
  > aws_secret_access_key = YOUR_AWS_SECRET_ACCESS_KEY
5. An existing SSH Key available at the AWS region where you'll run this playbook.


# Installation
1. Update `vars.yml`\
a. `region` The AWS region where you'll run this playbook.\
b. `instance_type` EC2 Instance type\
c. `ami_id` Ubuntu AMI ID (You can find it from the AMI picker while launching a New EC2)\
d. `ec2_count` The number of EC2 you want to launch\
e. `vpc_id` An existing VPC ID (You can find this from AWS Console VPC page)\
f. `vpc_subnet_id` An existing VPC Subnet ID (You can find this from AWS Console VPC page)\
g. `security_group` The name you want to give to the security group that'll be created by Ansible.\
h. `keypair_name` The SSH Key pair name that you've created at `Prerequisites #5`\
i. `ec2_group_name` The name you want to give to the EC2 created by Ansible.\
j. `ec2_ssh_username` SSH username (For Ubuntu AMI it'll be `ubuntu`)
2. Update `private_key_file` at `ansible.cfg` with its full path to the SSH key location that you've created at `Prerequisites #5`
3. Run the automation using `ansible-playbook -i hosts main.yml`
