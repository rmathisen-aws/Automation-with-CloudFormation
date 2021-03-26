# Automation with CloudFormation

**Create & Configure an EC2 Instance using CFN:**

We know that we'll be creating an EC2 Instance, so lets start by creating a Key Pair. \
We won't be using this Key Pair to connect to the Instance, but it will be required when we apply the CFN template.

\
EC2 → Network & Security → Key Pairs → Create Key Pair\
Name: A4L-Key \
File Format: pem \
Create Key Pair

\
CloudFormation → Create Stack

Prepare Template: Template is ready \
Specify Template: Upload a template file \
Choose File: Locate your ec2instance.yaml template \
Next

Whenever you Upload a template to CloudFormation, it will upload the template to an S3 Bucket that CFN creates automatically. \
You may notice a lot of buckets with the prefix cf- that get created in a region automatically. \
You can tidy things up and delete these if you want to.

Stack name: cfndemo1

Parameters: \
These are the Parameters that are specified within the ec2instance.yaml template! \
The template was written to have dafault values, which is the reason why there are pre-populated fields!

KeyName: A4L-Key \
LatestAmiId: default value \
SSHandWebLocation: default value \
Next

Configure Stack Options: these will be discussed later. \
Next

Review cfndemo1: \
Scroll to bottom

Capabilities: check box to acknowledge \
Create Stack

CFN views some resources it creates as "high risk". We are creating an Identity (IAM Role) \
Because it's an Identity, it's changing something that provides access to AWS, and CFN wants us to explicitly acknowledge that we want to create this resource.

Click the Refresh button to see the status being updated. \
The creation of these Stacks will take a few min.
