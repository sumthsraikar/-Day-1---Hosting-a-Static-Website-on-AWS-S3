#  Day 1 - Hosting a Static Website on AWS S3

Welcome to Day 1 of my 30-day tech blog journey! Today, I’ll be sharing how I hosted a static website (a neon-styled Tic-Tac-Toe game) using **Amazon S3**. It’s easy, scalable, and FREE under the AWS Free Tier.

---

##  What is a Static Website?

A static website is made up of HTML, CSS, and JavaScript files that don’t require a backend server. Perfect for:
- Portfolios
- Personal blogs
- Games (like mine )
- Product landing pages

---

## Tools Used

- **AWS S3 (Simple Storage Service)**
- **HTML/CSS/JS** project
- **Browser** to test it live

---

##  Steps to Host on AWS S3

### 1️⃣ Create an S3 Bucket

- Go to the [S3 Console](https://console.aws.amazon.com/s3/)
- Click **Create Bucket**
- Name it `blogday-01` (or anything unique)
- **Uncheck** “Block all public access”
- Click **Create**


![Screenshot 2025-06-06 230811](https://github.com/user-attachments/assets/120901d5-b6e3-489c-a1e6-5c62bd407419)


---

### 2️⃣ Upload Your Site Files

- Upload your `index.html` and any other files (`style.css`, `script.js`)
- Ensure file names match what you use in the HTML


![Screenshot 2025-06-06 224009](https://github.com/user-attachments/assets/78059541-ec97-46f0-8874-6a77cea9cc61)


---

### 3️⃣ Enable Static Website Hosting

- Go to **Properties** → **Static website hosting**
- Enable it
- Set:
  - Index Document: `index.html`
  - (Optional) Error Document: `error.html`
- Save


![Screenshot 2025-06-06 223823](https://github.com/user-attachments/assets/4539a88e-4b89-4a0c-9575-6c781e6f2e3b)


---

### 4️⃣ Make Files Public

You’ll need to update **permissions** to make the content publicly accessible:
- Go to **Permissions** tab
- Scroll to **Bucket Policy**
- Add this policy (replace with your bucket name):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::blogday-01/*"
    }
  ]
}


---

![Screenshot 2025-06-06 230853](https://github.com/user-attachments/assets/ab28bdfb-a684-46a2-af48-ee32e9c3dba9)

