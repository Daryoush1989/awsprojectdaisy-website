# AWS Project Daisy Website

## Overview

AWS Project Daisy Website is a static website hosting project that demonstrates secure delivery of a simple website through Amazon S3, CloudFront, Route 53, and AWS Certificate Manager.

The repository contains the static website files and documentation for the AWS hosting architecture. Before public release, review the website HTML for personal contact details and replace them with placeholders such as `<email-address>` if needed.

## Business Problem

Organizations often need a low-cost, secure, and globally available way to host static websites. This project demonstrates a common AWS pattern where S3 stores the website assets privately and CloudFront provides public HTTPS delivery.

## Architecture

High-level architecture:

```text
Browser
  -> Route 53 DNS
  -> CloudFront distribution with HTTPS
  -> Origin Access Control
  -> Private S3 bucket containing static assets
```

The project also uses ACM for TLS certificates and Route 53 for custom domain routing.

## AWS Services Used

- Amazon S3
- Amazon CloudFront
- CloudFront Origin Access Control
- AWS Certificate Manager
- Amazon Route 53
- AWS IAM / bucket policy controls

## Tools Used

- HTML
- Static image assets
- AWS Management Console
- Git and GitHub

## Security Features

- S3 bucket is intended to remain private.
- CloudFront uses Origin Access Control to access S3.
- HTTPS is provided through ACM.
- Public access is served through CloudFront rather than direct S3 object exposure.
- DNS is managed through Route 53.

## Deployment Summary

The repository documents a console-built static website deployment. The live/custom domain should be represented in public portfolio documentation as `<domain-name>` unless you intentionally want to disclose it. The current website HTML should also be reviewed for personal contact information before the repository is made public.

No deployment commands were run during this README refresh.

## Testing and Validation

Validation includes:

- Opening the root domain and `www` domain over HTTPS
- Confirming HTTP redirects or HTTPS enforcement through CloudFront settings
- Confirming CloudFront serves the default root object
- Confirming the S3 bucket is not publicly readable
- Testing the website on desktop and mobile screen sizes

## Evidence / Screenshots

The repository currently contains the website files rather than a dedicated evidence folder. If screenshots are added later, redact account IDs, distribution IDs if not needed, billing details, IAM details, private bucket policy information, and personal contact details.

## Cost Control

Static website hosting with S3 and CloudFront is typically low cost for small portfolio traffic. Costs can still come from Route 53 hosted zones, domain registration, CloudFront requests, data transfer, and S3 storage.

## Cleanup

Cleanup should include deleting CloudFront distributions after disabling them, removing Route 53 records or hosted zones when no longer needed, deleting ACM certificates where appropriate, and emptying/removing the S3 bucket after preserving any required evidence.

## Lessons Learned

- CloudFront and OAC are better public delivery patterns than exposing S3 buckets directly.
- HTTPS, DNS, caching, and origin security are all part of a professional static site deployment.
- Even simple websites benefit from clear cleanup and cost tracking.

## Future Improvements

- Add Infrastructure as Code using Terraform or AWS CDK.
- Add CI/CD for automatic static asset deployment.
- Add CloudWatch metrics or synthetic checks.
- Add cache invalidation workflow documentation.
- Add sanitized screenshots and architecture evidence.
- Replace personal contact details in the static HTML with placeholders before public release.
