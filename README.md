# Deploy Static Website on AWS

## Description

In this project, you will deploy a static website to AWS using S3, CloudFront, and IAM.

The files included are: 
- index.html - The Index document for the website.
- /img - The background image file for the website.
- /vendor - Bootssrap CSS framework, Font, and JavaScript libraries needed for the website to function.
- /css - CSS files for the website.

## Instructions

1. Create S3 bucket
  - bucket name: `udacity-website-amagnani`
  - uncheck: block all public access

2. Upload files and folders: index.html, img, vendor, css

3. Add Policy 
  ```json
  {
    "Version":"2012-10-17",
    "Statement":[
      {
        "Sid":"AddPerm",
        "Effect":"Allow",
        "Principal": "*",
        "Action":["s3:GetObject"],
        "Resource":["arn:aws:s3:::amzn-udacity-static-s3bucket "]
      }
    ]
  }
  ```

4. Configure S3 as Host Static Website 
  - entry page: index.html
  - error page: index.html

5. Create Distribution vith CloudFront
  - select delivery method: web
  - set `Origin Domain Name` your S3 bucket
  - set `Origin Path` empty (equivalent to “/”)

## Website URL

```http://amzn-udacity-static-s3bucket.s3-website-us-east-1.amazonaws.com/```

## Captures

- The S3 bucket is visible in the AWS Management console.

  <img width="1380" height="916" alt="1" src="https://github.com/user-attachments/assets/e3762d5f-a378-49cd-b5b2-215960f9384b" />

- All website files should be added to the S3 bucket.

  <img width="1898" height="954" alt="Screenshot from 2025-11-12 14-08-51" src="https://github.com/user-attachments/assets/b8e74b4d-f2e0-4cb6-bce4-14ef429360d9" />

- The S3 bucket is configured to support static website hosting.

  <img width="1531" height="360" alt="Screenshot from 2025-11-12 14-54-06" src="https://github.com/user-attachments/assets/755170bd-b4f3-4765-814e-629647df85cb" />


- The permission access to the bucket should be configured to allow public access.
- 
  <img width="1326" height="662" alt="image" src="https://github.com/user-attachments/assets/a9117824-b5fa-4212-929a-d2ea19335b9d" />

- CloudFront has been configured to retrieve and distribute website files.
  
<img width="738" height="222" alt="Screenshot from 2025-11-12 14-43-15" src="https://github.com/user-attachments/assets/975b848a-b270-4db5-9067-8ed08aa43aac" />

- Website publicly accessible
  
<img width="1909" height="953" alt="final" src="https://github.com/user-attachments/assets/e4b786e4-93bd-4e1a-a3e0-e92979f63676" />

  
