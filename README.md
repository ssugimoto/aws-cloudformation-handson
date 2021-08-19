# aws-cloudformation-handson

# ハンズオンのページ
## ハンズオン実施内容
AWS Hands-on for Beginners AWS 環境のコード管理 AWS CloudFormationで Web システムを構築する  
https://pages.awscloud.com/JAPAN-event-OE-Hands-on-for-Beginners-cfn-2020-reg-event-CP_707.html

## ハンズオンで作成されるもの
- ハンズオンで作成する構成は、https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/cfn-sample-templates.html の、「Amazon VPC の負荷分散型自動拡張型 WordPress ブログ」です。

- WordPressを動かすEC2のWebサーバとRDSのDBサーバを構成し、ELBで各サブネットに負荷分散します

# このリポジトリの説明

- ハンズオン実施内では、SubnetId, VPCID を途中で入力してymlを完成させていきます。
- そのymlの最終形ではなく、01_vpc.yml, 02_ec2.yml,03_rds.yml,04_elb.yml を順に `create-stack`で動くように修正しています。
- リポジトリにある yml を実行する例
```
aws cloudformation create-stack --stack-name handson-cfn --template-body file://01_vpc.yml  --profile AWSクレデンシャルのプロファイル名 --region リージョン名


aws cloudformation create-stack --stack-name handson-cfn-ec2 --template-body file://02_ec2.yml  --profile AWSクレデンシャルのプロファイル名 --region リージョン名


aws cloudformation create-stack --stack-name handson-cfn-rds --template-body file://03_rds.yml  --profile AWSクレデンシャルのプロファイル名  --region リージョン名


aws cloudformation create-stack --stack-name handson-cfn-elb --template-body file://04_elb.yml  --profile AWSクレデンシャルのプロファイル名  --region リージョン名

```

- cfn用のファイル
```
/cfn-handson
|--cfn
|  |--01_vpc.yml
|  |--02_ec2_userdata.sh
|  |--02_ec2.yml
|  |--03_rds.yml
|  |--04_elb.yml
```

# リンク

<!--https://pages.awscloud.com/rs/112-TZM-766/images/AWS-Hands-on-for-Beginners_CFn.pdf -->