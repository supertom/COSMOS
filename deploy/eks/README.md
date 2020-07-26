# Deploying COSMOS on AWS EKS

This guide explains how to deploy COSMOS on Amazon Web Services (AWS) Elastic Kubernetes Service (EKS). It covers the following topics:
* Creating an IAM policy for creating and managing EKS clusters.
* Creating an IAM user and assigning the IAM policy to it.
* Creating an EKS cluster as the IAM user.
* Deploying COSMOS on the EKS cluster.


## Creating an IAM policy for creating and managing EKS clusters

1. Using your root account, sign in to the AWS Console at https://console.aws.amazon.com/.

2. Navigate to the IAM service, Create policy page at https://console.aws.amazon.com/iam/home#/policies$new.

3. Click the JSON tab and paste the policy from the `iam_policy_eks_admin.json` file located along side this `README.md` file.

4. Click Review policy.

5. Click Save policy.


## Creating an IAM user and assigning the IAM policy to it.

1. Navigate to the IAM service, Add user page at https://console.aws.amazon.com/iam/home#/users$new.

2. Enter `eks_admin` as the user name.

3. Enable programmatic access.

4. Click Next: Permissions.

5. Click Attach existing policies directly.

6. Select the `eks_admin` policy from the list.

7. Click Next: Tags.

8. Click Next: Review.

9. Click Create user.


## Creating an EKS cluster as the IAM user

1. Install the `aws` CLI. Follow the instructions at https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html.

2. Configure AWS credentials. Use the Access Key and Secret Access Key of the `eks_admin` IAM user created earlier.
   ```
   $ aws configure
   ```

3. Install the `eksctl` CLI. Follow the instructions at https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html.

4. Create an EKS cluster named `cosmos-dev`.
   ```
   eksctl create cluster --name cosmos-dev
   ```

// WIP

## Deploying COSMOS on the EKS cluster

// TODO