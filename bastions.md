# Creating a Bastion Server
1. Create an EC2 instance. Follow steps 1 and 2 as normal. For step 3, select your VPC and then your public subnet. Enable 'Auto-assign public IP'. Continue as normal until step 6 - Create a security group, add a rule for port 22 which is restricted to your ip. Complete the configurations and launch.
2.  Amend the db instance security group such that port 22 is only open to the private and public ip addresses of the bastion instance.
3. Connect to the bastion instance via SSH.
4. Copy the access key (.pem file) into the bastion instance using scp.
```bash
scp -i key_name.pem key_name.pem ubuntu@bastion_ip:~/.ssh/
```
5. Navigate to the location of the key within the bastion server. Confirm the key is here using `ls`
6. Ensure read-only permissions have been applied to the key
```bash
sudo chmod 400 key_name.pem
```
7. Connect to the db instance
```bash
ssh -i ~/.ssh/key_name.pem ubuntu@db_private_ip
```
