# PRJ002-S3PreSignedURL
Learn how to securely store files in AWS by creating a private S3 bucket and setting up IAM permissions. This project walks you through making your bucket private, uploading files, and preparing for secure access with pre-signed URLs — all without using any code or SDKs. Perfect for beginners learning cloud storage and access control on AWS.

# Private S3 Bucket with Pre-Signed URL Access

## Overview

This project shows you how to create a **private S3 bucket** and set up **secure access controls** using AWS Identity and Access Management (IAM). The goal is to keep your files completely private while still allowing temporary access via **pre-signed URLs** — secure, time-limited links you can generate later (using the AWS Console or tools like the AWS CLI).

This is a great first project for anyone learning AWS cloud storage and security basics.

---

## Architecture

- **Amazon S3**: Stores your files in the cloud. We’ll configure the bucket to block all public access.
- **AWS IAM**: Manages access to your bucket. You’ll create a user who has permission to read files (and eventually generate pre-signed URLs).

These two services work together to keep your files private while still giving you full control over who can access them, and when.

---

## Getting Started

### 1. Create a Private S3 Bucket

1. Sign in to the [AWS Console](https://console.aws.amazon.com/)
2. Go to **S3**
3. Click **Create bucket**
4. Name your bucket something unique, like:  
   `my-private-bucket-yourname`
5. Leave the default Region
6. Under **Block Public Access settings**, make sure all boxes are **checked**  
   (This ensures your bucket stays private)
7. Click **Create bucket**

### 2. Upload a File

1. Click your bucket name
2. Click **Upload**
3. Add a file (PDF, image, etc.)
4. Click **Upload** again to confirm

> 🔒 Your file is now safely stored and **not accessible to the public.**

---

### 3. Create an IAM User with Read Access

1. Go to **IAM** in the AWS Console
2. Click **Users** > **Add users**
3. Enter a username like: `s3-access-user`
4. Select **Programmatic access**
5. Click **Next: Permissions**
6. Choose **Attach policies directly**
7. Search for and check **AmazonS3ReadOnlyAccess**
8. Continue through the prompts and click **Create user**
9. Save the **Access Key ID** and **Secret Access Key** (used for tools like the CLI or SDK later)

---

## Next Steps

You now have:
- A private S3 bucket
- A securely uploaded file
- An IAM user that can read (but not write or delete) files in that bucket

You're ready to explore how to generate **pre-signed URLs** in the future using tools like:
- The **AWS CLI**
- The **AWS SDK** (optional for more advanced users)

---

## Cleanup

To avoid any charges:
- Delete files inside your S3 bucket
- Delete the bucket itself
- Delete the IAM user if it's no longer needed

---

## License

MIT License


