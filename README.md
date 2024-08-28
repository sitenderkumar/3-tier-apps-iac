Terraform IaC Deployment of 3-Tier Application in AWS Cloud using AWS Secrets Manager for DB Credentials

This module contains Terraform code to deploy a 3-tier architecture on AWS.

You can fork this repository and clone it into your preferred IDE.

The deployment will create a new VPC with 6 subnets (2 for each of the web, application, and database tiers) to ensure high availability (HA).

    Web Tier: Instances will be deployed in public subnets.
    App and DB Tiers: Instances, including the RDS database, will be deployed in private subnets.

Only the web tier will receive traffic from the internet through an Internet Gateway.

The application and database tiers will not be connected to a NAT Gateway, meaning they won't have outbound internet access, such as for security patch installations.

Database credentials are securely stored in AWS Secrets Manager, and the Terraform code uses the data resource to fetch them. This is a security best practice, as it avoids hardcoding credentials in the code.
