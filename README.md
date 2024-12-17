
# Secure File Transfer with AWS S3 and IAM

Designed a secure file transfer system using AWS S3 with strict access controls.

## AWS Services
- S3
- IAM
- AWS CLI
## Key Achievements

- Configured secure S3 policies
- automated file transfers with AWS CLI
- implemented IAM roles for controlled access.
## Steps

# **Step1: Set Up an S3 Bucket**

1. **Create a Bucket**:
    - Go to the **S3 Console** and click **Create Bucket**.
    - Name your bucket (e.g., `secure-file-transfer-bucket`) and choose a region.
    - Enable **Bucket Versioning** for data protection.
    - Enable **Encryption** (e.g., SSE-S3 or SSE-KMS) to secure files.
2. **Block Public Access**:
    - Ensure **Block Public Access** is enabled (default setting).

# **Step2: Configure IAM Roles and Policies**

1. **Create an IAM Role**:
    - Go to the **IAM Console** > **Roles** > **Create Role**.
    - Select **AWS Service** and choose **EC2** or another service, depending on how files will be transferred.
    - Attach the **AmazonS3FullAccess** or a custom policy (explained below).
2. **Custom IAM Policy for Restricted Access**:
    - Create a policy to limit access to your bucket
    - Attach this policy to your IAM role or users.
    - **Assign IAM Role or User**:
        - Assign the IAM role to your EC2 instance or attach the policy to specific IAM users for secure file uploads/downloads.
    
    ### **3. Secure File Transfer Using AWS CLI**
    
    - **Install AWS CLI**:
        - Install the AWS CLI on your local system or EC2 instance.
        - Configure it with the IAM user’s credentials:
    - Provide:
        - Access Key ID
        - Secret Access Key
        - Region
        - Output format (default: `json`).
    - **Upload Files to S3**
    - **Download Files from S3**
    - **Automate Transfers**

# Step4: **Additional Security Measures**

- **Enable Server-Side Encryption**: Ensure all files are encrypted on S3 (use **SSE-S3** or **SSE-KMS** for additional security).
- **Set Bucket Policies**: Define strict policies to allow access only from specific IPs or VPCs
- **Enable Logging**: Turn on **S3 Server Access Logging** or **CloudTrail** to monitor file access and activities.

# **Step5: Test the Setup**

- **Test File Uploads/Downloads**: Use the AWS CLI or SDK to verify access and transfers.
- **Check Access Logs**: Confirm that access is logged in S3 or CloudTrail.
## Image

![DR Implementation Architecture](https://i.ibb.co/Zm2818R/Arch-diagram.png)
