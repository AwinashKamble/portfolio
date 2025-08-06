
# 🌐 AWS S3 Static Website Hosting Project

This project showcases how to host a professional portfolio website using **AWS S3 Static Website Hosting** with optional CDN and custom domain enhancements.

## 🚀 Project Overview

| Feature              | Tool/Service             |
|----------------------|--------------------------|
| Static Website       | AWS S3                   |
| CDN Optimization     | AWS CloudFront (optional)|
| Custom Domain        | AWS Route 53 (optional)  |
| SSL/HTTPS            | AWS Certificate Manager  |
| Permissions          | S3 Bucket Policy         |

---

## 📁 Project Structure

```
.
├── index.html
├── assets/
│   ├── styles.css
│   └── images, fonts, etc.
└── resume.pdf (optional)
```

---

## 🛠️ Steps to Deploy

### 1. Create S3 Bucket

- Go to AWS Console → S3 → Create bucket
- Use a **globally unique name**
- Uncheck **Block all public access**
- Enable **Static website hosting**

### 2. Set Static Website Hosting

- Index document: `index.html`
- Error document: `index.html` or blank

### 3. Set Bucket Policy for Public Access

```
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
```

### 4. Upload Website Files

- Upload all files from your project root (not inside a subfolder)
- Ensure `index.html` is at the **root** of the bucket

### 5. Access Website

- Use the **endpoint URL** shown in S3 → Properties → Static website hosting

```
http://awinash-portfolio.s3-website.ap-south-1.amazonaws.com/
```

---

## 🌐 Optional Enhancements

- **Add CloudFront**: Faster delivery + free SSL (HTTPS)
- **Route 53**: Use a custom domain like `yourname.dev`
- **ACM**: Attach SSL certificate for HTTPS

---

## 🧠 Learning Outcome

- AWS S3 configuration for web hosting
- Public permissions & security considerations
- End-to-end website deployment in the AWS Cloud

---

## 📄 License

This project is open-source and free to use under the MIT license.

---

✅ Created by Awinash - Cloud & DevOps Enthusiast  
🔗 Portfolio: http://awinash-portfolio.s3-website.ap-south-1.amazonaws.com/
