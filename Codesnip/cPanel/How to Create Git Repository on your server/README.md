###How to Create Git Repository on your server

---

***Step 1.*** Make sure you're aware of SSH access of your server. If you don't, please read this article.

[SSH access to your server](https://github.com/sag333ar/sag333ar.github.io/blob/master/cPanel/How%20to%20SSH%20connect%20to%20your%20shared%20server%20on%20mac/README.md)

---

***Step 2.*** SSH to your server. In my case, it is as follows.

```
ssh -p 2215 sagarr@sagarrkothari.com
```

---

***Step 3.*** Move to appropriate directory.

```
cd public_html/gitprojects/
```

---

***Step 4.*** Create a directory for your repository.

```
mkdir MyRepository.git
```

---

***Step 5.*** Move to folder/directory which you just created.

```
cd MyRepository.git
```

---

***Step 6.*** Initialize Git into that directory

```
git --bare init
```

---

***Step 7.*** Now switch to your `LOCAL` system. Create a folder to checkout.

```
cd /Volumes/Data/myLocalProjects
mkdir yourLocalCopyFolder
cd yourLocalCopyFolder
```

---

***Step 8.*** Initialize git & add remote `origin`

```
git init
git remote add origin ssh://sagarr@sagarrkothari.com:2215/home/sagarr/public_html/gitprojects/MyRepository.git
```

---

***Step 9.*** Make some changes in `LOCAL` repository & push it to your server-repository.

```
// Create t1 t2 t3 files
touch t1 t2 t3

// add t1 t2 t3 file to for committing
git add .

// commit your changes
git commit -m "add t1 t2 t3 files"

// push your changes to server
git push --all
```