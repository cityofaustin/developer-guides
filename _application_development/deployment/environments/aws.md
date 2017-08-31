---
title: AWS
position: 1
---

Amazon Web Service's S3 (_Simple Storage Service_) is a great way to host static content in the cloud. Common uses are for storing media (photo, video), data backups, and even complete static websites.

## Hosting a static site on S3

### Set the bucket as a website

1. Go to Your Bucket => Properties => Static website hosting
2. Enable the "Use this bucket to host a website" setting
3. Set your Index document path if you want the root bucket URL to resolve to your homepage (probably `index.html`)
4. Click "Save"

### Making your bucket public

Add the following setting at Your Bucket => Permissions => Bucket Policy

```
{
    "Version": "2008-10-17",
    "Statement": [
        {
            "Sid": "AllowPublicRead",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::coa-developer-guides/*"
        }
    ]
}
```

### Setting your homepage

