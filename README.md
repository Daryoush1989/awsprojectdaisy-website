awsprojectdaisy-website

Static website hosted on AWS S3 + CloudFront + Route 53 + ACM

🚀 Project Overview

This project hosts a fully static website using a modern and production-ready AWS architecture.
The site consists of a simple index.html homepage and an image (Dogs.JPG), delivered globally via CloudFront.

The aim of this project is to demonstrate hands-on cloud experience for future employers.

🧰 AWS Services Used

1. Amazon S3

Hosted the static website files (index.html, Dogs.JPG)
Public access blocked (secure by default)
Bucket configured as CloudFront origin

2. Amazon CloudFront

Global CDN distributing your website content
Connected to S3 bucket through an Origin Access Control (OAC)
HTTPS enforced

3. AWS Certificate Manager (ACM)

Issued an SSL certificate for
✔️ awsprojectdaisy.click
✔️ www.awsprojectdaisy.click

4. Amazon Route 53

Registered the domain: awsprojectdaisy.click
Created DNS records:
A record → CloudFront distribution
CNAME validation records for SSL certificate
Redirect www → root domain

🌐 Live Website

Site is deployed at:

🔗 http://awsprojectdaisy.click
🔗 http://www.awsprojectdaisy.click

(both working after DNS propagation)

📂 Files Included

File	Purpose
index.html	Main homepage
Dogs.JPG	Image displayed on the website

✨ What This Project Demonstrates

Hosting static sites on AWS
Using CloudFront for secure HTTPS delivery
Managing custom domains with Route 53
Creating and validating SSL certificates in ACM
Configuring advanced DNS (A, CNAME, alias)
Using OAC to secure S3 access

👤 Author

Daryoush1989
