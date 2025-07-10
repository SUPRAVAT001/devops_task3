# DevOps Task: Deploy Static Website using Jenkins and Docker

## 👨‍💻 Author
**Name**: Supravat Dash  
**GitHub**: [SUPRAVAT001/devops_task3](https://github.com/SUPRAVAT001/devops_task3)

---

## 📁 Project Structure

devops_task3/
├── static-website/
│ ├── index.html
│ ├── about.html
│ └── Dockerfile
└── README.md

markdown
Copy code

---

## 📌 Task Objectives

- Build a static website with `index.html` and `about.html`
- Containerize the website using Docker and Nginx
- Automate the deployment using Jenkins
- Host the site locally using Docker container (Nginx)

---

## 🔧 Technologies Used

- **Docker** (with `nginx:alpine`)
- **Git & GitHub**
- **Jenkins** (Freestyle project on WSL/Linux)
- **HTML** (for static pages)
- **Shell scripting** (for build commands)

---

## 🚀 Steps Followed

### 1. **Website Creation**
- Created `static-website/` directory with `index.html`, `about.html`
- Added basic HTML content for both pages

### 2. **Git & GitHub**
- Initialized Git repo
- Created branch: `add-html-pages`
- Committed HTML and Dockerfile
- Pushed to GitHub: [devops_task3 repo](https://github.com/SUPRAVAT001/devops_task3)
- Opened a **Pull Request** and **Issue** as part of the workflow

### 3. **Dockerization**
- Dockerfile content:

```Dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
Built the Docker image:


docker build -t mystaticweb .
Ran the container on port 5000:


docker run -d -p 5000:80 mystaticweb
Verified using:


curl http://localhost:5000
4. Jenkins Configuration
Created Freestyle Job: devops_task3

In Build Step → Execute Shell:

###jenkins build shell command
cd webbsite
docker build -t mystaticweb .
docker run -d -p 5000:80 mystaticweb
sleep 5
curl -I http://localhost:5000
