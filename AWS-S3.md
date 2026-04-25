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
