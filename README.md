**awsprojectdaisy-website**

**Static Website Hosted on AWS (S3 + CloudFront + Route 53 + ACM)**

🔗** Live Demo**

Project is deployed and publicly accessible here:

👉 https://awsprojectdaisy.click

🧾 **Project Overview**

This project demonstrates how to deploy a fully static website using modern, production-grade AWS cloud architecture.
It includes secure HTTPS hosting, global content delivery, and custom domain routing.

The goal of this project is to build real-world AWS experience and showcase professional cloud engineering skills to future employers.

🏗️ **AWS Architecture**

This project uses the following AWS services:

1. Amazon S3 — Static Website Storage

Stores all website files (index.html, images). <br>
Bucket kept private. <br>
Accessible only through CloudFront via OAC (Origin Access Control). 

2. Amazon CloudFront — Global CDN

Distributes content with low latency worldwide. <br>
Handles HTTPS enforcement. <br>
Caches static assets for performance.

Uses:

Origin Access Control (OAC) for secure S3 access. <br>
Alternate domain names (CNAMEs) for your domain. <br>
Default root object: index.html.

3. AWS Certificate Manager (ACM) — SSL/TLS

Provides free, auto-renewing SSL certificate. <br>
Secures awsprojectdaisy.click and www.awsprojectdaisy.click. <br>
Integrated with CloudFront for HTTPS.

4. Amazon Route 53 — DNS + Domain

Hosts the awsprojectdaisy.click domain.

DNS records:

A (Alias) → CloudFront (root domain) <br>
A (Alias) → CloudFront (www) <br>
Automatic ACM validation CNAMEs <br>
Enables reliable domain resolution globally.

5. Origin Access Control (OAC) — Security

Prevents S3 bucket from being public. <br>
Ensures only CloudFront can read website files. <br>
Modern replacement for bucket policies and OAI.

## 📁 File Structure

```
awsprojectdaisy-website/
│── index.html
│── Dogs.JPG
└── README.md
```


🚀 **Deployment Steps (High-Level)**
1. Create S3 Bucket

Name matches domain (awsprojectdaisy.click). <br>
Block public access. <br>
Upload site files.

2. Configure CloudFront

Origin → S3 bucket. <br>
Enable Origin Access Control.

Add CNAMEs:

awsprojectdaisy.click <br>
www.awsprojectdaisy.click <br>
Attach ACM certificate. <br>
Default root object = index.html.

3. Configure Route 53

A (Alias) → CloudFront (root) <br>
A (Alias) → CloudFront (www) <br>
ACM validation CNAMEs auto-generated <br>
DNS propagation (1–10 minutes)

4. Test Deployment

Desktop + mobile <br>
http/https <br>
root + www <br>
CloudFront cache invalidation if needed

🧪 **Testing**

Website was tested for:

✔ Mobile compatibility <br>
✔ Desktop compatibility <br>
✔ HTTPS encryption <br>
✔ Proper DNS routing <br>
✔ Fast global loading via CloudFront

✨ **Skills Demonstrated**

This project highlights:

Cloud architecture design <br>
Static website hosting on AWS <br>
DNS management (Route 53) <br>
SSL/TLS management (ACM) <br>
Content Delivery Networks (CloudFront) <br>
Secure hosting using OAC <br>
S3 bucket best practices <br>
Domain linking & custom hosting <br>
Real-world troubleshooting

📚 **Future Improvements**

Add CI/CD pipeline (GitHub Actions → S3) <br>
Add monitoring (CloudWatch + CloudTrail) <br>
Deploy using Infrastructure as Code (Terraform or AWS CDK) <br>
Add multiple environments (dev / prod)

👤 **Author**

Daryoush Waheed
