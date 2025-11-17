Below is a **Linux CentOS Lab Exercise** you can use for teaching or practice.
It includes objectives, prerequisites, step-by-step tasks, expected outputs, and verification steps.

---

# **🔧 Linux CentOS Lab Exercise**

## **Task: Create Two User Accounts, Set Passwords, and Switch Between Accounts**

---

## **🎯 Lab Objectives**

By the end of this lab, you will be able to:

* Create new user accounts in CentOS
* Set passwords for user accounts
* Switch between user accounts using `su` and `sudo`
* Verify user details

---

## **📌 Prerequisites**

* CentOS system (VM/Cloud/Local machine)
* Access to terminal
* Root or sudo privileges

---

# **📝 Exercise Instructions**

---

## **Step 1: Check Current User**

```bash
whoami
```

Expected output:

```
root
```

(or any user with sudo access)

---

## **Step 2: Create Two User Accounts**

Create **user1**:

```bash
sudo useradd user1
```

Create **user2**:

```bash
sudo useradd user2
```

---

## **Step 3: Set Passwords for the New Users**

Set password for **user1**:

```bash
sudo passwd user1
```

Set password for **user2**:

```bash
sudo passwd user2
```

You will be prompted to type and re-enter a new password.

---

## **Step 4: Verify User Accounts**

Check the last two created users:

```bash
tail /etc/passwd
```

Expected lines:

```
user1:x:1001:1001::/home/user1:/bin/bash
user2:x:1002:1002::/home/user2:/bin/bash
```

---

## **Step 5: Switch Between User Accounts**

### **Switch from root to user1**

```bash
su - user1
```

Check:

```bash
whoami
```

Output:

```
user1
```

### **Switch from user1 to user2 (password required)**

```bash
su - user2
```

Check:

```bash
whoami
```

Output:

```
user2
```

---

## **Step 6: Return Back to Original User**

Use:

```bash
exit
```

Run multiple times until you return to your original user session.

---

# **🧪 Verification Tasks**

✔ Confirm both users exist:

```bash
id user1
id user2
```

✔ Confirm home directories exist:

```bash
ls -l /home/
```

✔ Confirm switching works without errors.

---

