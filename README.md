# S3 Static Website Hosting with CDN and CI/CD
<strong>This guide outlines the steps to set up static website hosting using Amazon S3, CloudFront as a Content Delivery Network (CDN), and a CI/CD pipeline with AWS CodePipeline.
The visuals included help illustrate each step of the process.</strong>

- **Step 1: Create an S3 Bucket**<br>
<strong>First, create an S3 bucket that will host your static website. Ensure that you configure the bucket name correctly and keep it unique across all AWS accounts.</strong>
![s3 bucket](https://github.com/user-attachments/assets/c0d207b6-25c1-430b-bba7-7f40d050f4f0)

- **Step 2: Enable Static Website Hosting and Public Access**<br>
<strong> Once the bucket is created, enable static website hosting. This allows your S3 bucket to serve files over the web.</strong>
- **a) Enable Static Website Hosting**
![s3 enable static website](https://github.com/user-attachments/assets/4ffbae5d-540c-4a37-8f40-9ea9b6d0004d)
- **b) Enable Public Access**<br>
<Strong>Be sure to configure public access settings to allow visitors to access your website.</strong>
![s3 public access](https://github.com/user-attachments/assets/3a2437b4-2c19-412e-8970-2d4b65692bf3)

- **Step 3: Create a CloudFront Distribution**<br>
<strong>Create a CloudFront distribution that points to your S3 bucket. This serves as the CDN, improving the speed and performance of your website globally.</strong>
![cloudfront1](https://github.com/user-attachments/assets/9898243f-e760-46e7-8412-4e581b223043)

![cloudfront](https://github.com/user-attachments/assets/9f1309bf-f544-4a4a-ba85-aed82f71331f)

- **Step 4: Use CloudFront Origin Access Control (OAC)** <br>
<strong>To restrict direct access to your S3 bucket and ensure that only CloudFront can serve content, set up Origin Access Control (OAC).</strong>
![using OAC to access s3 bucket](https://github.com/user-attachments/assets/5564f1b5-23b8-42a8-9a10-dde114d98185)

- **Step 5: Set Up CI/CD with AWS CodePipeline**<br>
<strong>Create a CodePipeline to automate deployment whenever there are updates to your code in the source repository (e.g., GitHub).</strong>
![pipeline](https://github.com/user-attachments/assets/c9acf8f2-27b7-42a5-a9c6-a0a878a8b4ca)

# [Testing the setup]:<br>
<strong>After everything is set up, test your deployment to ensure that the static website is accessible via the CloudFront distribution.</strong>
![testing](https://github.com/user-attachments/assets/a6923e9f-6a88-4a56-8511-b6843af10398)

# [Updating Code in GitHub]:
<strong> When you make changes to your source code (e.g., updated HTML/CSS), push these changes to your GitHub repository.</strong>
![github updated](https://github.com/user-attachments/assets/47febda9-8d3f-4950-ac90-f62cfb12d267)

# [Automatic Triggering of CodePipeline]
<strong>Once you update your code in GitHub, the CodePipeline is triggered automatically to rebuild and deploy your website.</strog>
![after update pipeline trigger](https://github.com/user-attachments/assets/60840ea6-5b1e-4815-9131-e96764f811e6)

# [Verify Updated Website]
![after update website](https://github.com/user-attachments/assets/c641cf2e-03f6-40ae-8029-87188088b0a8)

# [Access Control Verification]
<strong>Finally, verify that direct access to the S3 bucket is denied due to the effective use of the Origin Access Control (OAC).</strong>
![OAC is enabled](https://github.com/user-attachments/assets/917a6bc7-d1ac-4014-bc7a-37ee1574420c)
