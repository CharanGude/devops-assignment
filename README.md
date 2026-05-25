# DevOps Assignment 🚀

This repository contains the DevOps assignment where you will deploy your application to the public internet using:

* Jenkins
* GitHub
* Docker
* Azure Kubernetes Service (AKS)

The Jenkins server and AKS cluster are already pre-configured.

---

# 📋 Prerequisites

Before starting, you need:

* A simple application
  *(A static website is completely fine)*

* A public GitHub repository containing:

  * Your application code
  * Updated `deployment.yaml`

---

# 📁 Step 1: Update the Kubernetes Deployment File

Inside this repository, you will find a file named:

```bash
deployment.yaml
```

Update the file as instructed in the comments.

### Important:

* Use **your own namespace**
* Update image names appropriately
* Verify deployment details before pushing

Example namespace format:

```yaml
namespace: yourname-ns
```

---

# 📤 Step 2: Push Code to GitHub

Push the following to your **public GitHub repository**:

* Application source code
* Updated `deployment.yaml`

---

# 🔐 Step 3: Login to Jenkins

Open the Jenkins server:

```text
https://tcjenkins.centralindia.cloudapp.azure.com/
```

---

# 🐳 Step 4: Add DockerHub Credentials in Jenkins

In Jenkins:

```text
Manage Jenkins
    → Credentials
        → System
            → Global Credentials
                → Add Credentials
```

Use:

* Your DockerHub username
* DockerHub Personal Access Token (PAT)

---

# 🔑 Step 5: Generate DockerHub PAT

Go to DockerHub:

```text
DockerHub Account
    → Account Settings
        → Personal Access Tokens
            → Generate New Token
```

### Required Permission

Enable:

```text
Read and Write
```

---

# ⚙️ Step 6: Update the Jenkinsfile

Inside the `Jenkinsfile`, update the following values:

* DockerHub credential ID
* Kubernetes namespace
* Docker image name
* GitHub repository URL

Example:

```groovy
credentialsId: 'your-dockerhub-credential'
```

---

# 🏗️ Step 7: Create Jenkins Pipeline

From the Jenkins home page:

```text
New Item
    → Pipeline
```

Then:

1. Scroll to the **Pipeline Script** section
2. Copy and paste the updated `Jenkinsfile`
3. Save the pipeline

---

# ▶️ Step 8: Run the Pipeline

Click:

```text
Build Now
```

To monitor logs:

```text
Open Build
    → Console Output
```

---

# 🌐 Step 9: Access Your Application

Once deployment succeeds, Jenkins logs will display:

```text
External IP
```

This IP is your application's public endpoint.

---

# ⚠️ If External IP Shows `<pending>`

Sometimes the LoadBalancer service takes time to provision.

If you see:

```text
<pending>
```

Simply rerun the pipeline:

```text
Build Now
```

The External IP should appear after the next successful deployment.

---

# ✅ Expected Outcome

By the end of this assignment, you will have:

* Built a Docker image
* Pushed the image to DockerHub
* Deployed the application to AKS
* Exposed the application publicly using a LoadBalancer service
* Automated deployment using Jenkins

---

# 📚 Technologies Used

* Jenkins
* Docker
* GitHub
* Microsoft Azure
* Kubernetes

---

# 🎯 Happy Learning! 🚀
