# Static-Web-Hosting-completed
This project sets up continuous integration and deployment for a static website using AWS CodePipeline, S3 for storage, CloudFront as the CDN, and GitHub as the source repository.

Setup Instructions

1.Create an S3 Bucket

. Go to the S3 console in AWS.

-Create a new bucket with a unique name (e.g., my-static-website-bucket).

![image](https://github.com/user-attachments/assets/7d0b738d-96cf-4e5e-a16b-51dd54b33dbd)


-Upload a html file in my-static-website-bucket.

![image](https://github.com/user-attachments/assets/7734c1a8-3ed4-4e8f-a3c4-2e74569a7113)


-Enable "Static website hosting" in the properties of the bucket

![image](https://github.com/user-attachments/assets/a5086afe-e94a-48db-8276-4a8d584997d1)


Set Up CloudFront

-In the CloudFront console, create a new CloudFront distribution.

![image](https://github.com/user-attachments/assets/ac25a35c-0d8c-4ad2-b528-932ad3f10a18)


-Set the origin to your S3 bucket.

![image](https://github.com/user-attachments/assets/19b7231f-33fe-4b31-b46a-4da4b05f786c)


-Configure the default cache behavior settings as needed.

-Set the appropriate bucket policy to allow public read access to the content (adjust if using CloudFront signed URLs).

![image](https://github.com/user-attachments/assets/f73ef14f-d8b2-4b53-b5a6-c18583c6bb45)


-Check the CloudFront distribution URL.

![image](https://github.com/user-attachments/assets/51021dce-a0fb-44e9-b0a2-53178ec4668d)


Connect GitHub Repository to CodePipeline Go to the CodePipeline console.

![image](https://github.com/user-attachments/assets/20590cb2-b39a-489b-beda-29d864f7ff8f)


-Create a new pipeline and select GitHub as the source provider.


![image](https://github.com/user-attachments/assets/549512af-3bb5-42df-98b5-372fb09c5a37)

-Add an S3 bucket as the deployment destination.

![image](https://github.com/user-attachments/assets/9ca98091-1915-4554-a5b2-91fbc4e987c8)


-Add S3 as the Deployment Provider

-In CodePipeline, add an S3 bucket as the deployment provider.

-Point it to the previously created S3 bucket.

-Deploy and Verify

![image](https://github.com/user-attachments/assets/33414776-a801-45dc-84d4-56ddb23d46e7)


-Commit changes to the GitHub repository.

![image](https://github.com/user-attachments/assets/7870c2bb-3dee-4fbe-9336-44927a72adf1)


-CodePipeline will automatically start and deploy the site to the S3 bucket.

-Access the deployed website through the CloudFront distribution URL.

![image](https://github.com/user-attachments/assets/c42d3195-4398-4c9f-b2e8-ed0eccaa344f)


CloudFront caching may delay changes; you can invalidate the cache if needed.
