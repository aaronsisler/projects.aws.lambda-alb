# projects.aws.lambda-alb

## Usage

```
$ curl loadb-LoadB-R7RVQD09YC9O-1401336014.eu-west-1.elb.amazonaws.com
Hello World!
```

## Steps

1. Deploy VPC
   - `aws cloudformation create-stack --stack-name vpc-alb-lambda --template-body file://vpc.yaml --capabilities CAPABILITY_NAMED_IAM`
   - tutorial for VPC can be found [here](https://medium.com/@t3chflicks/virtual-private-cloud-on-aws-quickstart-with-cloudformation-4583109b2433)
1. Deploy Service
   - `aws cloudformation create-stack --stack-name lambda-deploy --template-body file://lambda.yaml --capabilities CAPABILITY_NAMED_IAM`
1. Deploy Route53
   - `aws cloudformation create-stack --stack-name alb-lambda-route53 --template-body file://route53.yaml`

### Tips

`aws cloudformation delete-stack --stack-name lambda-deploy`

## Reference

1. Deploy VPC
   - `aws cloudformation create-stack --stack-name vpc --template-body file://reference/vpc.yaml --capabilities CAPABILITY_NAMED_IAM`
   - tutorial for VPC can be found [here](https://medium.com/@t3chflicks/virtual-private-cloud-on-aws-quickstart-with-cloudformation-4583109b2433)
1. Deploy Service
   - `aws cloudformation create-stack --stack-name service --template-body file://reference/service.yaml --capabilities CAPABILITY_NAMED_IAM`
1. Deploy Service with CORS enabled
   - `aws cloudformation update-stack --stack-name service --template-body file://reference/service_CORS.yaml --capabilities CAPABILITY_NAMED_IAM`

---

This project was created by [T3chFlicks](https://t3chflicks.org) - A tech focused education and services company.
