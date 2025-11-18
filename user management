# Task: Create group `devs`, create user `alice` in that group, set password, check password/account status, then delete the user and group.
---

## 1) Create the group

**Command**

```bash
sudo groupadd devs
```

**Check group exists**

```bash
getent group devs
# or
grep '^devs:' /etc/group
```

**Expected output (example)**

```
devs:x:1001:
```

---

## 2) Create the user and assign primary group `devs`

**Using `useradd` (RHEL/CentOS/most Linux)**

```bash
sudo useradd -m -g devs -s /bin/bash alice
```

Options:

* `-m` create home `/home/alice`
* `-g devs` set primary group
* `-s /bin/bash` set shell

**Debian alternative (friendlier interactive):**

```bash
sudo adduser --ingroup devs alice
```

**Verify user & group membership**

```bash
id alice
# Expected example output:
# uid=1002(alice) gid=1001(devs) groups=1001(devs)
getent passwd alice
```

---

## 3) Set the password for `alice`

**Interactive**

```bash
sudo passwd alice
# then type password and confirm
```

**Non-interactive (useful for scripts)**

```bash
echo 'alice:StrongP@ssw0rd' | sudo chpasswd
```

**Lock / Unlock password**

```bash
sudo passwd -l alice   # lock account (disable password)
sudo passwd -u alice   # unlock account
```

---

## 4) Check password/account status

Use multiple checks — `passwd -S`, `chage -l`, and the shadow entry.

**a) Summary status**

```bash
sudo passwd -S alice
```

**Example output**

```
alice P 2025-11-17 0 99999 7 -1 (Password set, last change date...)
```

Meaning:

* `P` = password set (LK = locked)
* date = last password change
* fields: lastchg min max warn inactive expire

**b) Password aging / expiry details**

```bash
sudo chage -l alice
```

**Example output**

```
Last password change                                    : Nov 17, 2025
Password expires                                        : never
Password inactive                                       : never
Account expires                                         : never
Minimum number of days between password change         : 0
Maximum number of days between password change         : 99999
Number of days of warning before password expires      : 7
```

**c) Shadow file entry (root only)**

```bash
sudo grep '^alice:' /etc/shadow
```

**Example output (fields separated by `:`)**

```
alice:$6$...hashed...:18600:0:99999:7:::
```

* 2nd field beginning `$6$...` = hashed password; `!` or `*` often indicates locked account.

---

## 5) Delete the user and optionally remove home and mail spool

**Remove user but keep files**

```bash
sudo userdel alice
```

**Remove user and remove home directory & mail spool**

```bash
sudo userdel -r alice
```

**Verify user deleted**

```bash
getent passwd alice || echo "user alice not found"
# or
id alice 2>/dev/null || echo "user alice not found"
```

---

## 6) Delete the group

**Command**

```bash
sudo groupdel devs
```

**Verify**

```bash
getent group devs || echo "group devs not found"
```

---

## Quick exam-style Q&A (short answers)

**Q: How do you create a group named `devs`?**
A: `sudo groupadd devs`

**Q: How to create user `alice` with primary group `devs` and a home directory?**
A: `sudo useradd -m -g devs -s /bin/bash alice` (or `sudo adduser --ingroup devs alice` on Debian)

**Q: How to set `alice`'s password non-interactively?**
A: `echo 'alice:MyPass123' | sudo chpasswd`

**Q: How to check `alice`'s password status and aging?**
A: `sudo passwd -S alice` and `sudo chage -l alice`

**Q: How to delete `alice` and remove home directory?**
A: `sudo userdel -r alice`

**Q: How to delete the group `devs`?**
A: `sudo groupdel devs`

---
