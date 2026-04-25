# AWS-Machine-Learning
AWS Machine Learning certfication preparation

<img width="1057" height="577" alt="image" src="https://github.com/user-attachments/assets/f32e250c-f2df-4d4b-9001-456f45a8a6f8" />

# Data Engineering
```
```
# AWS Billing Alarms
25/04/2026 AWS Billing Alarms using service Billing and cost management servce . created a new budget monthly $20 and set the mail notification  we can pass multiple mail id by , seperated .
```
```

# ☁️ AWS S3 Overview

## What is AWS S3?

Amazon S3 (Simple Storage Service) is a cloud-based storage service provided by AWS that allows you to store and retrieve any amount of data from anywhere in the world.

---

## 📌 Definition

Amazon S3 is an object storage service used to store files such as images, videos, documents, backups, and application data in the cloud with high durability, scalability, and security.

---

## 🧠 Simple Meaning

Think of S3 as a **Google Drive for developers**, but designed for applications instead of personal personal use.

---

## 🧱 Basic Components

### 1. Bucket
- A container that stores files  
- Like a folder in a computer  

### 2. Object
- The actual file stored in a bucket  
- Example: `image.jpg`, `video.mp4`, `data.json`  

### 3. Key
- Unique path/name of the object inside the bucket  
- Example: `images/profile/user1.jpg`

---

## ⚙️ Key Features

- 📈 Highly scalable (stores unlimited data)  
- 🔒 Secure (IAM policies, encryption)  
- 💪 Very durable (data is safe even if hardware fails)  
- ⚡ Fast access from anywhere in the world  
- 💰 Pay only for what you use  

---

## 🚀 Common Use Cases

- Storing images and videos for websites/apps  
- Backup and restore systems  
- Hosting static websites (React, Angular)  
- Data archiving (logs, old files)  
- Sharing files securely via links  

---

## 🧾 Simple Summary

AWS S3 is a cloud storage service used to store files safely, access them anytime, and integrate with applications easily.

<img width="1860" height="890" alt="image" src="https://github.com/user-attachments/assets/1e42a35b-d639-4c5c-a451-0935cd6b0f9c" />

# 🔄 AWS S3 Lifecycle Rules – Step-by-Step Creation

## ☁️ Service
Amazon S3 (Simple Storage Service)

---

## 🎯 Objective
Create a lifecycle rule to automatically:
- Move files to cheaper storage
- Delete old/unnecessary files

---

## 🛠️ Step 1: Login to AWS Console
- Go to AWS Console
- Search for **S3**
- Open Amazon S3 dashboard

---

## 📦 Step 2: Create or Select Bucket

### Option A: Create New Bucket
1. Click **Create bucket**
2. Enter bucket name (must be unique)
3. Select region
4. Keep default settings (or configure as needed)
5. Click **Create bucket**

### Option B: Use Existing Bucket
- Click on an existing bucket name

---

## ⚙️ Step 3: Open Lifecycle Configuration

1. Inside the bucket
2. Go to **Management** tab
3. Scroll to **Lifecycle rules**
4. Click **Create lifecycle rule**

---

## 🏷️ Step 4: Enter Rule Name
- Example:
  - `log-cleanup-rule`
  - `image-archive-rule`

---

## 🎯 Step 5: Choose Rule Scope

Select one:
- Apply to **entire bucket**
- Apply to **specific prefix**
  - Example: `logs/`, `images/`
- Apply using **tags**

---

## 🔄 Step 6: Configure Transition Actions

Enable "Transition current versions of objects"

### Example:
- After **30 days** → Move to **Standard-IA**
- After **90 days** → Move to **Glacier**
- After **180 days** → Move to **Deep Archive**

---

## 🗑️ Step 7: Configure Expiration Actions

Enable "Expire current versions of objects"

### Example:
- Delete objects after **365 days**

---

## 🔁 Step 8: (Optional) Versioning Rules

If versioning is enabled:
- Expire previous versions
- Delete delete markers

---

## 👀 Step 9: Review Rule

- Check:
  - Rule name
  - Scope
  - Transition settings
  - Expiration settings

---

## ✅ Step 10: Create Rule
- Click **Create rule**

---

## 🔄 S3 Lifecycle Flow Example


Day 0–30 → Standard Storage
Day 31–90 → Standard-IA
Day 90–180 → Glacier
Day 365 → Deleted

## ⚠️ Important Notes

- Rules run automatically (once daily)
- Changes are not immediate
- Deleted data cannot be recovered (unless versioning is enabled)
- Helps reduce storage cost

---

## 🧾 Summary

S3 Lifecycle Rules automate:
- Storage optimization
- Cost reduction
- Data cleanup
# 🛠️ AWS S3 Policy Generator Tool

## ☁️ What is this tool?

The AWS Policy Generator is an online tool used to **create IAM policies and S3 bucket policies easily without manually writing JSON**.

👉 Tool link:  
https://awspolicygen.s3.amazonaws.com/policygen.html

---

## 📌 Definition

It is a web-based tool provided by AWS that helps users generate correct policies for:
- IAM users/roles  
- S3 buckets  
- SNS, SQS, and other AWS services  

All policies are generated in **JSON format automatically**.

---

## 🧠 Simple Meaning

Think of it like:
👉 “Form-based policy builder”

Instead of writing JSON manually, you:
- Select service  
- Choose actions  
- Add resource (bucket/ARN)  
- Generate policy  

---

## ⚙️ What you can create using this tool?

- IAM Policies  
- S3 Bucket Policies  
- SNS Topic Policies  
- SQS Queue Policies  
- VPC Endpoint Policies  

---

## 🚀 How to use it (Step-by-Step)

### 1. Open the tool
👉 https://awspolicygen.s3.amazonaws.com/policygen.html

---

### 2. Select Policy Type
Choose:
- IAM Policy OR  
- S3 Bucket Policy  

---

### 3. Configure Policy Details

Fill the required fields:

- **Effect** → `Allow` or `Deny`  
- **AWS Service** → `S3`  
- **Actions** → e.g.  
  - `s3:GetObject` (read)  
  - `s3:PutObject` (upload)  
- **ARN / Resource** → bucket or object path  

---

### 4. Add Statement
- Click **Add Statement**
- You can add multiple rules in one policy

---

### 5. Generate Policy
- Click **Generate Policy**
- The tool creates JSON automatically

---

### 6. Copy & Use Policy
- Copy generated JSON  
- Paste into S3 bucket → **Permissions → Bucket Policy**

---

## 🧱 Example Output (S3 Public Read Policy)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-bucket/*"
    }
  ]
}

---

## 🧾 Simple Summary

AWS Policy Generator is a visual tool that helps generate correct AWS policies (especially S3 bucket policies) without manually writing JSON, making it easier and faster for developers.

