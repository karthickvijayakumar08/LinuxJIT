✅ File Permission – Lab Exercise
________________________________________
🔹 LAB 1: View File Permissions
Step 1: Create a file
touch file1.txt
Step 2: Check permissions
ls -l file1.txt
Q1: What are the default permissions?
________________________________________
🔹 LAB 2: Change Permissions Using Symbolic Method
Step 1: Remove read permission for others
chmod o-r file1.txt
Step 2: Add execute permission for user
chmod u+x file1.txt
Step 3: Remove write permission for group
chmod g-w file1.txt
Step 4: Verify
ls -l file1.txt

 	🔹 LAB 3: Change Permissions Using Numeric (Octal) Method
Step 1: Give 755 permission
chmod 755 file1.txt
Step 2: Change to 640
chmod 640 file1.txt
Step 3: Try 777
chmod 777 file1.txt

________________________________________
🔹 LAB 4: Directory Permissions
Step 1: Create a directory
mkdir labdir
Step 2: Give full access
chmod 777 labdir
Step 3: Remove execute permission
chmod a-x labdir
Step 4: Try entering directory
cd labdir
👉 Should fail (x is required to enter).
Step 5: Restore execute only
chmod a+x labdir
 	

 LAB 5: Ownership (chown)
Step 1: Create user (if allowed)
sudo useradd student2
Step 2: Change file owner
sudo chown student2 file1.txt
Step 3: Change group
sudo chown :student2 file1.txt
Step 4: Both owner & group
sudo chown student2:student2 file1.txt
________________________________________
🔹 LAB 6: Default Permissions (umask)
Step 1: Check current umask
umask
Step 2: Create a new file
touch test.txt
ls -l test.txt
Q3: What permissions were applied?
(Use formula: permissible – umask)

LAB 7: Test Permissions Behavior
Step 1: Remove all permissions
chmod 000 file1.txt
Step 2: Try accessing
cat file1.txt
👉 Permission denied.
Step 3: Restore permissions
chmod 644 file1.txt
