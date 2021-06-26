# INNOGEEKS- Session Task
📔 Get to know your fellow Geeks!

## Go ahead and add an .md file about yourself

### 1️⃣ Fork the repo 

### 2️⃣ Clone the repo locally

```
  git clone https://github.com/<your-github-username>/Getting-started-with-git-github-2021.git
```

### 3️⃣ Track the original repository as a remote of the fork 

```
  git remote add --track master upstream https://github.com/InnogeeksOrganization/Getting-started-with-git-github-2021.git
  git fetch upstream
```
    
### 4️⃣ Create a new branch for your changes with same name as that of your Github username

```
  git checkout -b <your-github-username> upstream/master
```
    
    
### 5️⃣ Create a `.md` file with format `<github username>.md` in:
  - *Batch(2020-2024)* directory if you are from this batch
  - *Batch(2019-2023)* directory if you are from this batch

  You can add the following information about yourself:
  - About
  - Place
  - Skills
  - Interests
  - Links where others can catch up with you in the universe
  - Previous contributions if any
  - Projects that you are most proud of
  
### 6️⃣ Add, commit, and push the changes

```
  git add .
  git commit -m "README: Add info about <your-github-username>"
```

### 7️⃣ Push changes to your branch

```
  git push -u origin <your-github-username>
```

### 8️⃣ Submit your pull request
