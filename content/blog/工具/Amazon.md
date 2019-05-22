---
title: "Amazon服务"
date: 2019-05-13T015:46:29+08:00
draft: true
---
## 源队列
## 死信队列
当一条消息初次消费失败，消息队列 RocketMQ 会自动进行消息重试；达到最大重试次数后，若消费依然失败，则表明消费者在正常情况下无法正确地消费该消息，此时，消息队列 RocketMQ 不会立刻将消息丢弃，而是将其发送到该消费者对应的特殊队列中。
- 在消息队列 RocketMQ 中，这种正常情况下无法被消费的消息称为**死信消息**（Dead-Letter Message），存储死信消息的特殊队列称为**死信队列**（Dead-Letter Queue）。

## AWS SAM CLI 安装
```sh
# 安装
pip install --user aws-sam-cli
# error
Building wheels for collected packages: regex
  Building wheel for regex (setup.py) ... error
# 安装
sudo apt-get install python3-dev
[bqzhu@pc ~]$ sam --version
SAM CLI, version 0.16.0
[bqzhu@pc ~]$
```

## SAM local
### Quick Start
- bug: ClassNotFound
```sh
# sam local start-api
REPORT RequestId: bdf7cf95-38bf-40c4-bf8c-627d554b7aaa  Duration: 7.68 ms       Billed Duration: 100 ms Memory Size: 128 MB     Max Memory Used: 2 MB   
START RequestId: 01789ffb-41f2-4287-8306-1ddd3f7924ce Version: $LATEST
java.lang.ClassNotFoundException: helloworld.App
        at java.net.URLClassLoader.findClass(URLClassLoader.java:382)
        at java.lang.ClassLoader.loadClass(ClassLoader.java:424)
        at java.lang.ClassLoader.loadClass(ClassLoader.java:357)
        at java.lang.Class.forName0(Native Method)
        at java.lang.Class.forName(Class.java:348)

END RequestId: 01789ffb-41f2-4287-8306-1ddd3f7924ce
# sam build
# sam local start-api
2019-05-15 16:52:13 Mounting /home/bqzhu/Desktop/iCoBPC/Hello/.aws-sam/build/HelloWorldFunction as /var/task:ro,delegated inside runtime container
START RequestId: ead433c3-b641-410c-8722-2aab731fc209 Version: $LATEST
END RequestId: ead433c3-b641-410c-8722-2aab731fc209
REPORT RequestId: ead433c3-b641-410c-8722-2aab731fc209  Duration: 2245.08 ms    Billed Duration: 2300 ms        Memory Size: 128 MB     Max Memory Used: 7 MB
```

## SNS消息筛选策略
- [SNS with filter policy](https://github.com/awslabs/serverless-application-model/blob/master/examples/2016-10-31/lambda_sns_filter_policy/README.md)

## 
arn:aws-cn:lambda:cn-northwest-1:148543509440:function:demo-sam-HelloWorldFunction-1VCNHC3U8ZLOE
- How to publish msg to SNS from lambda -- https://stackoverflow.com/questions/51966972/aws-publishing-to-sns-from-lambda-function
- VPC
## Reference
- https://help.aliyun.com/knowledge_detail/87277.html
- [Introducing Simplified Serverless Application Deployment and Management](https://amazonaws-china.com/cn/blogs/compute/introducing-simplified-serverless-application-deplyoment-and-management/)
- [使用 sam 在本地调试 aws lambda 程序
](https://www.jianshu.com/p/6b836881d570)

- [AWS lambda by VS code](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/building-lambda.html)
- [AWS Serverless Application Model (SAM)](https://github.com/awslabs/serverless-application-model/blob/master/versions/2016-10-31.md)
- [Invoking AWS Lambda functions via Amazon SNS](https://amazonaws-china.com/cn/blogs/mobile/invoking-aws-lambda-functions-via-amazon-sns/)
- [Lambda function does not publish to SNS or update dynamodb](https://forums.aws.amazon.com/thread.jspa?threadID=267921)
- [learn-aws-lambda](https://github.com/dwyl/learn-aws-lambda)
- [AWS-SAM-Tutorial](https://github.com/chenr2/AWS-SAM-Tutorial)