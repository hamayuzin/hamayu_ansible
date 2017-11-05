ansibleで　AWSと　rails環境作れるようにしたい

## 最初の設定

#### awsの認証情報
```
export AWS_SECRET_ACCESS_KEY=
export AWS_ACCESS_KEY_ID=
```

#### awsの認証情報
aws.yml
```
---
- hosts: localhost
  connection: local
  gather_facts: no
  roles:
    - role: aws/ec2
  vars:
    ami_image: ami-2a69be4c # 2017-11-04設定
    key_name: 
    tag_name: 
    instance_type: "t2.micro"
    device_name: "/dev/xvda"
    device_type: "gp2"
    volume_size: 30
    region: ap-northeast-1
    security_group:
      - 
    vpc_subnet_id: 
    assign_public_ip: yes
```

## aws周り
```
ansible-playbook -i hosts/aws/ec2.py aws.yml --private-key=/Users/hamayu/.ssh/aws_hamayu.pem
```
