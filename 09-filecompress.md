
🧪 File Compression – Lab Exercise (Linux)

Commands Used: zip,gzip, gunzip, tar

Here are the **Linux `zip` command examples** you can use:

---

## **1. Create a ZIP file**

```
zip file.zip file1.txt file2.txt
```

This creates **file.zip** containing *file1.txt* and *file2.txt*.

---

## **2. Zip a folder (directory)**

```
zip -r folder.zip foldername/
```

`-r` → recursive (includes all files/subfolders)

---

## **3. Create a ZIP file with multiple files**

```
zip mybackup.zip *.txt
```

Zips **all .txt files**.

---

## **4. Add password to ZIP file**

```
zip -e secure.zip file.txt
```

It will ask for a password.

---

## **5. Exclude files while zipping**

```
zip -r project.zip project/ -x "*.log"
```

Excludes all **.log** files.

---

## **6. Update existing zip file**

```
zip -u file.zip newfile.txt
```

---

## **7. View ZIP file contents**

```
unzip -l file.zip
```

---

## **8. Extract a ZIP file**

```
unzip file.zip
```

---


✔ Exercise 1: Compress a File Using gzip

1.Create a sample file

2.echo "This is a test file" > sample.txt

3.Compress it

4.gzip sample.txt

5.Verify output

6.ls -l sample.txt.gz

7.Decompress

8.gunzip sample.txt.gz




✔ Exercise 2: Compress a Folder Using tar + gzip

(archive + compress)

1.Create folder

2.mkdir project

3.echo "file1" > project/a.txt

4.echo "file2" > project/b.txt

5.Compress folder

6.tar -czvf project.tar.gz project/

7.Verify archive

8.tar -tf project.tar.gz

✔ Exercise 3: Extract tar.gz Archive

tar -xzvf project.tar.gz

✔ Exercise 4: Create Uncompressed tar Archive (No Compression)

tar -cvf backup.tar project/

Extract:

tar -xvf backup.tar




