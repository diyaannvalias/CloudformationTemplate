# CloudformationTemplate
**This template will do the below things:**
 
1. Create a VPC with public and private subnets, route tables, and a NAT gateway. Configure the route tables with appropriate routes and associate the subnets with their corresponding route tables.

2. Deploy an EC2 instance within the private subnet, ensuring accessibility only through a bastion host. Additionally, establish an RDS instance in the private subnet.

3. Create a CloudFront distribution that serves objects from an S3 bucket and associate a WAF.

# To package and upload cloudformation template to s3

aws cloudformation package \
  --template /path_to_template/template.json \
  --s3-bucket mybucket \
  --output-template-file packaged-template.json \
  --use-json
