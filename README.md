My Static Website
A simple static website hosted on AWS S3 and delivered via CloudFront for better performance and security.

Project Overview
This project demonstrates how to:
✅ Host a static website using Amazon S3.
✅ Configure CloudFront for CDN and HTTPS.
✅ Manage website files using GitHub.

Live Demo
🔗 Website URL: https://d2dnt040r3cumy.cloudfront.net/

Getting Started
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/SuhaniSharmaJoshi/MystaticWebsite.git
cd MystaticWebsite
2. Upload Files to S3
Log in to AWS S3 Console.

Create a bucket (e.g., mystaticwebsite).

Enable Static Website Hosting in the bucket settings.

Upload your website files (index.html, styles.css, etc.).

Set the bucket policy to allow public access:

json
Copy
Edit
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::mystaticwebsite/*"
    }
  ]
}
3. Configure CloudFront
Open AWS CloudFront and create a distribution.

Select your S3 bucket as the origin.

Enable "Restrict Bucket Access" if you want to make S3 private.

Copy the CloudFront URL and test the website.

Deploying Updates
Using GitHub
Add changes to Git:

bash
Copy
Edit
git add .
git commit -m "Updated website content"
git push origin main
Upload the updated files to S3 manually or automate with a CI/CD pipeline.

Project Structure
bash
Copy
Edit
/MystaticWebsite
│── index.html      # Main HTML file
│── styles.css      # CSS styles
│── script.js       # JavaScript file (optional)
│── images/         # Image assets
│── README.md       # Project documentation
Technologies Used
🔹 AWS S3 – Hosting static files
🔹 AWS CloudFront – CDN for fast delivery
🔹 GitHub – Version control & repository

Troubleshooting
CloudFront Shows "Access Denied"
Ensure your S3 bucket policy allows s3:GetObject for Principal: *.

In CloudFront, check if the origin settings are correctly set to your S3 bucket.

Git Push Fails
Run git pull origin main --rebase before pushing.

Ensure the GitHub repository URL is correctly set with git remote -v.

Contributing
Feel free to fork this repository and contribute!

Author
👤 Suhani Sharma Joshi
📧 [SuhaniSharmaJoshi/README.md, suhanibetu2@gmail.com]
