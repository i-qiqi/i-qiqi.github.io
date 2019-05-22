---
title: "Design Implementation"
date: 2019-05-21T19:35:10+08:00
draft: true
---

## Two Chnnels
- `/context-sharing/output` : 企业EIS发送事件给Bullitin
- `/context-sharing/input` : Bullitin事件发送企业EIS

## 协作事件

```json
｛
  "subject" : "xxx",
  "action" : "xxx",
  "attrs" : {
      "Test": {
            "Type": "String",
            "Value": "TestString"
          },
          "TestBinary": {
            "Type": "Binary",
            "Value": "TestBinary"
          }
  }
｝
{
  "Records": [
    {
      "EventSource": "aws:sns",
      "EventVersion": "1.0",
      "EventSubscriptionArn": "arn:aws:sns:us-east-1::/context-sharing/output",
      "Sns": {
        "Type": "Collabotation",
        "MessageId": "95df01b4-ee98-5cb9-9903-4c221d41eb5e",
        "TopicArn": "arn:aws:sns:us-east-1:123456789012:ExampleTopic",
        "Subject": "example subject",
        "Message": "example message",
        "Timestamp": "1970-01-01T00:00:00.000Z",
        "SignatureVersion": "1",
        "Signature": "EXAMPLE",
        "SigningCertUrl": "EXAMPLE",
        "UnsubscribeUrl": "EXAMPLE",
        "MessageAttributes": {
          "Test": {
            "Type": "String",
            "Value": "TestString"
          },
          "TestBinary": {
            "Type": "Binary",
            "Value": "TestBinary"
          }
        }
      }
    }
  ]
}
```
