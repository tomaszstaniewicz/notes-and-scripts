1. Log into instance using ssh
    > chmod 400 ./key-pairs/ssh.pem
    > ssh -i ./key-pairs/ssh.pem ec2-user@ec2-3-120-185-60.eu-central-1.compute.amazonaws.com

2. Show drives 
    > lsblk
3. Create files system on drive
    >  sudo mkfs -t ext4 /dev/xvdb
4. Create directory /data
    > sudo mkdir /data
5. Mount disk to data directory 
    > sudo mount /dev/xvdb /data
6. Mount EBS volume on every system reboot (and other instructions)
    https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-using-volumes.html     
7. Show disk formatting
    > sudo file -s /dev/xvdb
           
8. Unmounting drive
    > sudo umount /data

## EBS vs Instance Storage
 EBS volume is network drive but Instance Storage is a disk physically attahced to the ec2 machine
 so Instance Storage is faster but ephemeral. Good to use for caches        
 
## EBS vs EFS
EBS - only in one AZ
EFS - shared in multiple AZ (paid only for used memory)
    - content management
    - web serving 
    - data sharing
    - Wordpress
    - 3times more expensive than EBS
    
          
                  