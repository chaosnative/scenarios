#### AWS Node Failure Chaos

* To achieve node failure chaos under an availability zone litmus makes use of aws sdk to call ec2 start and stop to bring back the services

* The `aws-permission.json` contains larger permission for the instance. Following contain the minimised permission for the same.

* The minimized permission required are to perform the chaos should be:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ec2:StartInstances",
                "ec2:StopInstances",
                "ec2:describeInstances"
            ],
            "Resource": "arn:aws:ec2:*:*:instance/*",
            "Condition": {
                "StringEquals": {
                    "aws:ResourceTag/Owner": "${aws:username}"
                }
            }
        },
        {
            "Effect": "Allow",
            "Action": "ec2:DescribeInstances",
            "Resource": "*"
        }
    ]
}
```

Refer: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_ec2_tag-owner.html
