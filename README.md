ansibleで　AWSと　rails環境作れるようにしたい

## 最初の設定

#### awsの認証情報
```
export AWS_SECRET_ACCESS_KEY=
export AWS_ACCESS_KEY_ID=
```

#### 設定ファイルいじる
```
ec2-server.yml
aws.yml
```
.exampleははずしてください。


#### サーバー周り
`hosts/ec2-servers`に下記記入
```
[servers]
ip address各
52.111.111.22 的な
```

`config/`に　
serverアクセス用の`authorized_key`
github用の`id_rsa`
を置いておく

## コマンド
### ec2たてるとか
```
ansible-playbook -i hosts/aws/ec2.py aws.yml --private-key=/Users/hogehoge/.ssh/fugafuga.pem
```

### サーバーにnginxいれるとか
```
ansible-playbook -i hosts/ec2-servers  ec2-server.yml --private-key=/Users/hogehoge/.ssh/fugafuga.pem
```
