awsprojectdaisy-website

Static Website Hosted on AWS (S3 + CloudFront + Route 53 + ACM)

🔗 Live Demo

https://awsprojectdaisy.click

🧾 Project Overview

This project demonstrates how to deploy a fully static website using modern, production-grade AWS cloud architecture.
It includes secure HTTPS hosting, global content delivery, and custom domain routing.

The goal of this project is to build real-world AWS experience and showcase professional cloud engineering skills to future employers.

🏗️ AWS Architecture

This project uses the following AWS services:

1. Amazon S3 — Static Website Storage

Stores all website files (index.html, images).
Bucket kept private.
Accessible only through CloudFront via OAC (Origin Access Control).

2. Amazon CloudFront — Global CDN

Distributes content with low latency worldwide.
Handles HTTPS enforcement.
Caches static assets for performance.

Uses:

Origin Access Control (OAC) for secure S3 access.
Alternate domain names (CNAMEs) for your domain.
Default root object: index.html.

3. AWS Certificate Manager (ACM) — SSL/TLS

Provides free, auto-renewing SSL certificate.
Secures awsprojectdaisy.click and www.awsprojectdaisy.click.
Integrated with CloudFront for HTTPS.

4. Amazon Route 53 — DNS + Domain

Hosts the awsprojectdaisy.click domain.

DNS records:

A (Alias) → CloudFront (root domain)
A (Alias) → CloudFront (www)
Automatic ACM validation CNAMEs
Enables reliable domain resolution globally.

5. Origin Access Control (OAC) — Security

Prevents S3 bucket from being public.
Ensures only CloudFront can read website files.
Modern replacement for bucket policies and OAI.

🧩 File Structure

awsprojectdaisy-website/
│── index.html
│── Dogs.JPG
└── README.md

🚀 Deployment Steps (High-Level)

1. Create S3 Bucket

Name matches domain (awsprojectdaisy.click).
Block public access.
Upload site files.

2. Configure CloudFront

Origin → S3 bucket.
Enable Origin Access Control.

Add CNAMEs:

awsprojectdaisy.click
www.awsprojectdaisy.click
Attach ACM certificate.
Default root object = index.html.

3. Configure Route 53

A (Alias) → CloudFront (root)
A (Alias) → CloudFront (www)
ACM validation CNAMEs auto-generated
DNS propagation (1–10 minutes)

4. Test Deployment

Desktop + mobile
http/https
root + www
CloudFront cache invalidation if needed

🧪 Testing

Website was tested for:

✔ Mobile compatibility
✔ Desktop compatibility
✔ HTTPS encryption
✔ Proper DNS routing
✔ Fast global loading via CloudFront

✨ Skills Demonstrated

This project highlights:
Cloud architecture design
Static website hosting on AWS
DNS management (Route 53)
SSL/TLS management (ACM)
Content Delivery Networks (CloudFront)
Secure hosting using OAC
S3 bucket best practices
Domain linking & custom hosting
Real-world troubleshooting

📚 Future Improvements

Add CI/CD pipeline (GitHub Actions → S3)
Add monitoring (CloudWatch + CloudTrail)
Deploy using Infrastructure as Code (Terraform or AWS CDK)
Add multiple environments (dev / prod)

👤 Author

Daryoush Waheed
