# Allowing IAM access to only a specific subdomain on Route 53

We are going to create an IAM ploicy for a user to access only spefic subdomain hosted zone on Route 53.

Suppose you have company(anishababu.tech) with branches in different states(for example: kerala.anishababu.tech, delhi.anishababu.tech) and you have to allow each branch admin to only access to their branch DNS zone. You can setup a IAM user with subdomain zone access privilges.

![456666](https://user-images.githubusercontent.com/100779249/159098593-8d5f4c8b-6b1d-4eb0-8d73-565826cbb516.png)

## Steps to configure

* Step1:

Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/

* Step2: 

Create IAM user via Identity and Access Management (IAM) > Users > Add users option.

* Step3: Create a policy for the user to access its branch subdomain.

* Step4: 
