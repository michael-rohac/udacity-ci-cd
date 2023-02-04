# First Exercise - main.yml

**Get all public IP addresses of running instances**

```shell
$ echo "[ubuntu]" > inventory.txt 
$ aws ec2 describe-instances --query 'Reservations[*].Instances[*].PublicIpAddress' --profile udacity-ansible --filters "Name=tag:Project,Values=ansible" --output text >> inventory.txt
```

**Run ansible main.yml**

```shell
$ ansible-playbook -i inventory.txt main.yml --private-key ~/udacity-ansible-key.pem
```

# Second Exercise - main-remote.yml

**Get all public IP addresses of running instances**

```shell
$ echo "[all]" > inventory.txt 
$ aws ec2 describe-instances --query 'Reservations[*].Instances[*].PublicIpAddress' --profile udacity-ansible --filters "Name=tag:Project,Values=ansible" --output text >> inventory.txt
```

**Run ansible main.yml**

```shell
$ ansible-playbook -i inventory.txt main-remote.yml --private-key ~/udacity-ansible-key.pem
```