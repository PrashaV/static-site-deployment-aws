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

Go to **Permissions > Bucket Policy** tab and paste:(replace your-bucket-name)

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

## Step 3: Create a CloudFront Distribution

1. Open the **CloudFront Console** and click “Create Distribution”

2. Under Origin domain, select your S3 static website endpoint (CloudFront will auto-fill the name)

3. Origin Shield: Leave disabled

4. Scroll through the Default cache behavior — you can keep the default settings for a simple setup

5. **Web Application Firewall** (WAF): Optional, you can skip this unless you want advanced security

6. Click “Create Distribution”

Once deployed, your website will be available globally via a secure HTTPS CloudFront domain, such as: https://d12345678.cloudfront.net

---

## Deployment Summary
1. **Created S3 Bucket** with static website hosting enabled
2. **Uploaded index.html** to the root of the bucket
3. Configured **bucket policy** for public read access
4. **Deployed CloudFront Distribution**, linked to the S3 bucket
5. Set up **HTTPS via ACM (Amazon Certificate Manager)**
6. Tested site accessibility through CloudFront domain

---

## Highlights
- Hosted a static website with Amazon S3
- Configured secure public access to the S3 bucket using a tailored bucket policy
- Enabled global content delivery and caching using Amazon CloudFront to reduce latency and improve load times
- Configured HTTPS encryption via CloudFront for secure, scalable access to the static website across all regions
- Deployed a website without the need for a traditional backend or web server

---

## How to Reproduce

To deploy a similar site yourself:

1. Clone or fork this repo
2. Create an index.html, a basic HTML website file
3. Follow the steps in `deploy-notes.md` 
4. Host on AWS with your own bucket and CloudFront setup

---

## Screenshots

## S3 Static Website Hosting
![S3 static website hosting](https://github.com/user-attachments/assets/32af0c5a-dfbb-49c0-8283-4633b73da101)

## AWS Cloudfront Console
![AWS Console_Cloudfront](https://github.com/user-attachments/assets/c27c717e-2ef8-436e-89b5-e8b51b0a5e3e)

## Static Website Deployed on Cloudfront
![Cloudfront_Static website hosting](https://github.com/user-attachments/assets/19f802c6-6614-464b-8313-e3f47648b28f)

---

🔗 [LinkedIn](https://www.linkedin.com/in/prashanthie-velmurugan/)  
📧 vgprashanthie@gmail.com

