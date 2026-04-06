# 🚀 Creating a Fusion Analytics Warehouse (FAW) Instance

This document provides a complete step-by-step guide to creating a **Fusion Analytics Warehouse (FAW)** instance in Oracle Cloud Infrastructure (OCI), including IAM setup, user synchronization, and instance configuration.

---

## 🧠 Overview

FAW setup involves:

* Creating a user in Fusion (HCM)
* Syncing the user with OCI
* Configuring IAM (Groups & Policies)
* Creating and validating the FAW instance

---

## 👤 Step 1: Create User in HCM

Create a new user with the following details:

**Username:**
`FAWExtractUser`

**Required Roles:**

* Application Implementation Administrator
* ESS Administrator Role
* Upload & Download Data Role
* REST API Extract Privilege

---

## 🔐 Step 2: Login to OCI

Login to OCI using administrator credentials.

![Login](images/faw-instance/step01-login.png)

---

## 🔄 Step 3: Sync User to OCI

Navigate to:

```
Identity & Security → Domains → <your-domain>
→ Oracle Cloud Services → Fusion Applications Cloud Service
```

Click on **Import → Import** to sync the user.
![ Goto fusion applications](images/faw-instance/step02-GOto-fusion-applications.png)
![Import User](images/faw-instance/step03-import-user.png)

---

## 👥 Step 4: Create Group & Add User

Navigate to:

```
Domains → Groups → Create Group
```

* Group Name: `FAW_ADMIN`
* Add user: `FAWExtractUser`

![Group Creation](images/faw-instance/step04-group-creation.png)

---

## 📜 Step 5: Create Policy

Navigate to:

```
Identity & Security → Policies → Create Policy
```

* Enable **Manual Editor**
* Use the following policy:

```
Allow group id <group_ocid> to manage all-resources in tenancy
```

![Policy Creation](images/faw-instance/step05-policy-creation.png)

---

## 📋 Step 6: Verify Policy

Ensure the policy is created successfully.

![goto Policy](images/faw-instance/step06-goto-policy.png)
![Policy List](images/faw-instance/step07-policy-list.png)

---

## 🔓 Step 7: Login with FAW User

Logout from admin and login using:

* Username: `FAWExtractUser`
![login to oci again](images/faw-instance/step08logging-in-again.png)
---

## 📂 Step 8: Navigate to FAW Service

Go to:

```
OCI → Analytics & AI → Fusion Analytics Warehouse
```

![Navigation](images/faw-instance/step09-menu-navigation.png)
![Navigate-to-ur-compartment](images/faw-instance/step10-navigation-to-compartment.png)

---

## ⚙️ Step 9: Create FAW Instance

Click on **Create Instance** and fill:

* Compartment
* Display Name
* Description
* Notification Email

![Instance Form](images/faw-instance/step11-instance-form.png)

---

## 🔑 Step 10: Configure Authentication

* Provide Fusion URL (Dev URL)
* Select **Password-Based Authentication**
* Enter credentials
* Click **Test Connection**

![Authentication](images/faw-instance/create-instance-fusion-creds.png)


---

## 🌐 Step 11: Network Configuration

* Set Network Access to **Public**

![Network](images/faw-instance/Create-instance-ADW-creds.png)

---

## 🏷️ Step 12: Tagging (Optional)

Add tags such as:

* CreatedBy
* CreatedOn

![Tagging](images/faw-instance/create-instance-tags-optional.png)

---

## 🧱 Step 13: Final Creation

Click **Create Instance**

![Instance Page](images/faw-instance/step07-instance-page.png)

⏳ Instance creation takes approximately **30–40 minutes**

---

## ✅ Step 14: Instance Created

Once completed, verify:

* FAW URL
* Analytics Cloud access
* Autonomous Data Warehouse

![Instance Created](images/faw-instance/instance-created.png)

---

## 💡 Key Takeaways

* User synchronization from Fusion to OCI is mandatory
* IAM (Groups & Policies) setup is critical
* Authentication must be validated before creation
* FAW integrates multiple components (Fusion + ADW + Analytics)

---

## 🔗 Part of Portfolio

This is part of my Oracle Data & Analytics Journey:

👉 https://github.com/Rufus9640/oracle-data-journey
