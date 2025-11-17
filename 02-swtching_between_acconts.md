---

# 🔧 **CentOS Lab Exercise: Switching Between User Accounts**

## 🎯 **Objective**

Learn how to switch between user accounts in a CentOS system using the `su` command.

---

## 📌 **Prerequisites**

* A CentOS machine or VM
* At least **two user accounts** already created
* Access to the **root account** or any existing user

(If you need, I can also create a lab to create these users.)

---

# 📝 **Lab Tasks**

---

## **Step 1: Check Current User**

Run:

```bash
whoami
```

Expected output:

```
root
```

(or whichever user you are logged in as)

---

## **Step 2: Switch from root to another user**

Example: switch to **user1**

```bash
su - user1
```

Check:

```bash
whoami
```

Expected output:

```
user1
```

---

## **Step 3: Switch from one user to another**

If you are logged in as **user1**, switch to **user2**:

```bash
su - user2
```

Check:

```bash
whoami
```

Expected output:

```
user2
```

---

## **Step 4: Return back to the previous user**

Use:

```bash
exit
```

Each `exit` will take you back **one level**.

Example:

* From user2 → back to user1
* From user1 → back to root

---

## **Step 5: Confirm Your Session Level**

Type:

```bash
whoami
```

and

```bash
pwd
```

This confirms:

* Which user you are
* Which home directory you are in

---

# 🧪 **Verification Tasks**

1. Switch to user1 and verify the username using:

   ```bash
   whoami
   ```
2. Switch to user2 and verify again.
3. Use `exit` twice and confirm you returned to root.
4. Run:

   ```bash
   id
   ```

   to confirm identity and groups.

---

# ⭐ **Optional Challenge**

Check login history of users:

```bash
last
```

---
