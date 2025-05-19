# AWS-static-site-deployment
This project showcases a fully deployed static website hosted on **Amazon S3** and distributed globally using **CloudFront**. It's designed to be secure, scalable, and fast — perfect for personal portfolios or small static applications.

## Live Demo
🔗 [View the Live Website](https://d306m6ixj1e2ue.cloudfront.net/)  
---

## Tech Stack
- **Amazon S3** – Static website hosting
- **CloudFront** – Content Delivery Network (CDN) for speed and HTTPS
- **AWS Certificate Manager** – Free SSL/TLS encryption
- **Optional: WAF** – Web Application Firewall for basic protection

---

## Step-by-step guide on how I deployed the site using AWS S3 + CloudFront

## Pre-requisites 
An AWS account (Free-tier) 
A HTML file (e.g., portfolio.html linked below)

## Step 1: Set up an Amazon S3 Bucket for Static Hosting

1. Navigate to Amazon S3 Console > Click “Create Bucket”
- Enter a unique Bucket Name (e.g., your-bucket-name)
- Choose a preferred AWS Region (ideally close to your location)
- Uncheck “Block All Public Access” to allow public access to website files

2. Open your newly created bucket and upload your website files (index.html, style.css, etc.)

3. Go to the Properties tab and scroll to Static website hosting
- Click Edit, enable static website hosting
- Ensure index.html is uploaded to the root level of the bucket (not inside a folder)
- Copy the Website endpoint URL — this will serve as your website’s publicly accessible address

## Step 2: Set Bucket Policy for Public Read Access

Go to **Permissions > Bucket Policy** tab and paste: (listed under bucket-policy-code)

## Step 3: Create a CloudFront Distribution

Open the CloudFront Console and click “Create Distribution”
- Under Origin domain, select your S3 static website endpoint (CloudFront will auto-fill the name)
- Origin Shield: Leave disabled
- Scroll through the Default cache behavior — keep the default settings for a simple setup
- Web Application Firewall (WAF): Optional — skip unless you need advanced security
- Click “Create Distribution”

Once deployed, your website will be available globally via a secure HTTPS CloudFront domain, such as:
[https://d12345678.cloudfront.net ](https://d306m6ixj1e2ue.cloudfront.net/)

## Deployment Summary

- Created S3 Bucket with static website hosting enabled
- Uploaded index.html to the root of the bucket
- Configured bucket policy for secure public read access
- Deployed CloudFront Distribution, linked to the S3 bucket
- Set up HTTPS using ACM (Amazon Certificate Manager)
- Tested site accessibility through the CloudFront domain

## Highlights
- Hosted a static website with Amazon S3
- Configured secure public access via a tailored bucket policy
- Enabled global content delivery and caching using Amazon CloudFront to reduce latency
- Configured HTTPS encryption via CloudFront for secure, scalable access
- Deployed a website without a traditional backend or web server

## To deploy a similar site:

- Clone or fork this repo
- Create an index.html file (basic HTML website)
- Follow the steps in deploy-notes.md
- Host your version on AWS using an S3 bucket and CloudFront

## Screenshots

## S3 Static Website Hosting

![S3 static website hosting](https://github.com/user-attachments/assets/ed503ff6-a6b8-4800-a3b6-3252aee3cbad)

## AWS CloudFront Console 

![AWS Console_Cloudfront](https://github.com/user-attachments/assets/0754681b-575a-461e-a314-1ca2bc0fd3d3)

## Static Website Deployed on CloudFront

![Cloudfront_Static website hosting](https://github.com/user-attachments/assets/3d08217f-0c6f-47e0-84ff-528908248643)

## CODE

## bucket-policy-code

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

## Contact
🔗 LinkedIn – prashanthie-velmurugan
📧 vgprashanthie@gmail.com





