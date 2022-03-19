# Allowing IAM access to only a specific subdomain on Route 53

We are going to create an IAM policy for a user to access only specific subdomain hosted zone on Route 53.

Suppose you have company(anishababu.tech) with branches in different states(for example: kerala.anishababu.tech, delhi.anishababu.tech) and you have to allow each branch admin to only access to their branch DNS zone. You can setup a IAM user with subdomain zone access privileges.

![456666](https://user-images.githubusercontent.com/100779249/159098593-8d5f4c8b-6b1d-4eb0-8d73-565826cbb516.png)

## Steps to configure

* Step1:

Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/

* Step2: 

Create IAM user via Identity and Access Management (IAM) > Users > Add users option.

* Step3: Create a policy for the user to access its branch subdomain.

IAM policy
```{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "S0",
            "Effect": "Allow",
            "Action": [
                "route53:GetHostedZone",
                "route53:ChangeResourceRecordSets",
                "route53:ListResourceRecordSets"
            ],
            "Resource": "arn:aws:route53:::hostedzone/<Hosted zone ID of domain from route 53>"
        },
        {
            "Sid": "S1",
            "Effect": "Allow",
            "Action": [
                "route53:ListHostedZones",
                "route53:GetHostedZoneCount",
                "route53:ListHostedZonesByName"
            ],
            "Resource": "*"
        }
    ]
}
```

You can view the Hosted zone ID via Route 53 > Hosted zones as shown below:

![zone](https://user-images.githubusercontent.com/100779249/159102455-7e52d7d5-17eb-4ec1-8b25-a831b2bfd91a.png)

* Step4: Attach the poilcy to desired IAM user.
