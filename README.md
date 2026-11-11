exp 1
Objective

To understand and implement the fundamentals of version control using Git and GitHub, covering local repository setup, staging, committing, branching, pushing code to a remote repository, managing repository visibility (Public/Private), creating Pull Requests (PR), and merging changes.

Tools/ Software Required

Operating System: Windows 10 / 11
Version Control System: Git (Git CLI / Git Bash)
Code Editor / IDE: Visual Studio Code / IDLE / Plain Text Editor
Programming Environment: Python 3.x
Remote Repository Platform: GitHub (Web Browser)

Industry Relevance and Applications

Distributed Version Control: Enables distributed teams across the globe to collaborate simultaneously on the same codebase without overwriting each other's work.
Traceability & History: Every single modification is snapshotted with a commit hash, author info, and timestamp, allowing easy debugging, auditing, and rollback of regressions.
CI/CD Automation: Modern DevOps pipelines (GitHub Actions, Jenkins, GitLab CI) trigger automated build, test, and deployment workflows directly on Git events (e.g., git push, pull_request).
Code Quality & Peer Reviews: Pull Requests (PRs) enforce code review guidelines, branch protection rules, and automated status checks before merging to production branches (main/master).
Security & Access Governance: Managing repository visibility (Private vs. Public) ensures intellectual property, proprietary algorithms, and sensitive enterprise configurations remain protected.

Description

Git is a Distributed Version Control System (DVCS) designed to handle everything from small to very large projects with speed and efficiency. Unlike centralized systems, every developer has a full local copy of the repository history.

Core Architecture of Git
Working Directory: The local folder on your computer where files are actively edited (e.g., ex.py, ex1.py).
Staging Area (Index): An intermediate holding area where changes are prepared and organized before creating a commit snapshot.
Local Repository (.git): The local database containing all committed versions, logs, and branch pointers.
Remote Repository (GitHub): The cloud-hosted central repository used for team collaboration, sharing, and deployment.
Repository Visibility:
Public Repository: Visible to anyone on the internet. Ideal for open-source software and public portfolio projects.
Private Repository: Accessible exclusively to the owner and explicitly invited collaborators. Suitable for proprietary source code.
Changing Visibility: Configured via GitHub Repository Settings $\rightarrow$ Danger Zone $\rightarrow$ Change visibility.

Command list with explanation

Command
Explanation
git init
Initializes a new local Git repository in the current directory and creates the hidden .git folder.
git status
Displays the status of the working tree, showing staged, untracked, and modified files.
git add <file> / git add .
Stages specific files or all modified/new files into the staging index.
git commit -m "<msg>"
Records the staged snapshot into the local repository history with a descriptive commit message.
git branch
Lists all existing branches in the local repository and highlights the current branch.
git branch <branch_name>
Creates a new branch at the current commit.
git checkout <branch_name>
Switches the working tree to the specified branch.
git checkout -b <branch_name>
Creates a new branch and immediately switches to it.
git remote add origin <url>
Connects the local repository to a remote GitHub repository named origin.
git push -u origin <branch_name>
Uploads local branch commits to the remote repository and sets the upstream tracking branch.
git pull origin <branch_name>
Fetches and integrates changes from the specified remote branch into the current local branch.
git merge <branch_name>
Merges changes from the specified branch into the currently active branch.
git log
Displays the detailed commit history, including commit hashes, authors, timestamps, and messages.



Procedure

Step 1: Installing and Configuring Git
Download and install the 64-bit Git setup for Windows from https://git-scm.com/download/win.
Follow the setup wizard and ensure "Git from the command line and also from 3rd-party software" is selected.
Open Terminal / PowerShell / Command Prompt and configure your username and email using:
git config --global user.name "Your Name"
git config --global user.email your_email@domain.com

Step 2: Initializing the Local Git Repository
Navigate to the desired project folder on your local machine (e.g., C:\Users\urk23co2021\Desktop\ex1).
Initialize a new Git repository in the current directory using the command:
git init
Verify that the hidden .git directory is created.

Step 3: Creating and Staging Project Files
Create your source code files such as ex.py and ex1.py inside the project folder.
Check the status of untracked files in the working directory:
git status
Add all files to the staging area (index) to prepare them for commit:
git add . (or git add ex.py)

Step 4: Committing Changes Locally
Save the staged changes to your local Git repository history with an informative message:
git commit -m "initial commit"
Verify the commit history using:
git log

Step 5: Creating Remote Repository and Linking with Local Git
Log in to your GitHub account (https://github.com).
Click New repository, set the repository name as Devops-Ex1, and choose initial visibility.
Link your local repository to the newly created remote repository using:
git remote add origin https://github.com/bleslinjony/DEVOPS-EXP-1.git
Verify the linked remote URL:
git remote -v

Step 6: Pushing Local Commits to GitHub (Main Branch)
Push your local main branch commits to the remote GitHub repository:
git push -u origin main
Open the GitHub repository URL in the browser to confirm that the files ex.py and ex1.py are uploaded.

Step 7: Creating and Switching to a New Branch
Create a new branch named main1 and switch to it using:
git checkout -b main1
Confirm the active branch using:
git branch

Step 8: Modifying Files and Committing in the New Branch
Open and modify the file ex.py with your code (e.g., print("URK23CO2021")).
Check the modified status:
git status
Stage the modified file and commit the changes:
git add ex.py
git commit -m "commit"

Step 9: Pushing the New Branch to GitHub
Push the new branch main1 and its commit to the remote repository:
git push origin main1
Refresh the GitHub repository page to verify that the main1 branch has been pushed.

Step 10: Creating and Merging a Pull Request (PR) on GitHub
Navigate to your repository page on GitHub (https://github.com/bleslinjony/DEVOPS-EXP-1.git).
Click Compare & pull request next to the prompt for branch main1.
Review the code differences and commit details, then click Create pull request.
Click Merge pull request and click Confirm merge to incorporate the changes into the main branch.

Step 11: Managing Repository Visibility (Public / Private)
Go to the repository page on GitHub $\rightarrow$ Click Settings.
Scroll down to the Danger Zone section at the bottom of the page.
Click Change visibility $\rightarrow$ Select Make Private (or Make Public).
Type the full repository name https://github.com/bleslinjony/DEVOPS-EXP-1.git to verify and confirm the action.
Click I understand, change repository visibility.


exp 2
Objective

To design and create a Python Flask web application, containerize it using Docker, test the container locally on specified ports, and deploy the container image to Docker Hub for public accessibility and cross-platform execution.

Tools/ Software Required

Operating System      : Windows 10/11 / Linux / macOS
Programming Language  : Python 3.9+
Web Framework         : Flask 2.2.5
Containerization Tool : Docker Desktop / Docker Engine (v20.x or higher)
Container Registry    : Docker Hub Account (User: klassy01)
Code Editor           : Visual Studio Code / Any Text Editor
Testing Tools         : Web Browser (Google Chrome / Edge), Windows PowerShell / CMD

Industry Relevance and Applications

1. Environment Parity (Dev-to-Prod Consistency):
   Solves the infamous "it works on my machine" problem by bundling the application 
   code, dependencies, runtime, and system libraries together into an immutable 
   container image.

2. Microservices Architecture:
   Modern enterprise applications are broken into small, modular microservices. 
   Docker enables independent development, containerization, and scaling of each 
   service.

3. CI/CD Pipeline Automation:
   Docker images serve as standard build artifacts in automated Continuous 
   Integration and Continuous Deployment (CI/CD) pipelines (e.g., GitHub Actions, 
   Jenkins, GitLab CI), simplifying testing and staging rollouts.

4. Cloud-Native Scalability:
   Container images hosted on public or private registries (such as Docker Hub, 
   AWS ECR, or Google Artifact Registry) can be deployed instantly to cloud-native 
   orchestration engines like Kubernetes, AWS ECS, Google Cloud Run, or Azure Container Apps.

5. Resource Efficiency:
   Unlike traditional virtual machines (VMs) that require full guest operating 
   systems, Docker containers share the host OS kernel, resulting in ultra-fast 
   startup times (seconds) and lower memory overhead.

Description

Containerization is an operating-system-level virtualization technique that allows 
applications to run in isolated user spaces known as containers.

Key Concepts:
- Flask: A lightweight, modular Python micro-web framework used for building web 
  applications and RESTful APIs quickly without unnecessary boilerplate.
- Dockerfile: A plain text document containing ordered instructions used by the 
  Docker daemon to automatically build a container image.
- Docker Image: A lightweight, standalone, executable software package that 
  includes everything needed to run an application (code, runtime, libraries, settings).
- Docker Container: A live, runnable instance of a Docker image isolated from the 
  host system and other containers.
- Port Forwarding / Binding (-p host_port:container_port): Bridges network traffic 
  from the host machine's external port to the listening internal port of the container.
- Docker Hub: A cloud-based registry service that allows developers to store, share, 
  and distribute Docker container images globally.

Command list with explanation

1. docker build -t flask-docker-app .
   - Builds a Docker image using the Dockerfile located in the current directory (represented by .).
   - Flag '-t flask-docker-app' specifies a name (tag) for the generated image.

2. docker run -p 5000:5000 flask-docker-app
   - Launches a container from the 'flask-docker-app' image.
   - Flag '-p 5000:5000' binds port 5000 of the host machine to port 5000 of the container.

3. docker run -p 5050:5000 flask-docker-app
   - Runs the container with alternative port binding if host port 5000 is occupied.
   - Forwards host port 5050 to container port 5000.

4. docker run -d --name <name> -p 5000:5000 <image>
   - Flag '-d' runs the container in detached (background) mode.
   - Flag '--name' assigns a friendly name to the container instance.

5. docker ps
   - Displays all currently running containers with their IDs, image names, port mappings, and status.

6. docker ps -a
   - Lists all containers on the system, including running, stopped, and exited containers.

7. docker stop <container_id_or_name>
   - Gracefully stops an active running container.

8. docker rm <container_id_or_name>
   - Deletes one or more stopped containers to free up system resources.

9. docker login
   - Prompts for username and password to authenticate the local Docker CLI with Docker Hub.

10. docker tag flask-docker-app <username>/flask-docker-app:latest
    - Creates an alias/reference tag that prefixes the image name with the Docker Hub username,
      which is required before pushing to Docker Hub.

11. docker push <username>/flask-docker-app:latest
    - Uploads the tagged container image and its layers to the user's public Docker Hub repository.

12. docker pull <username>/flask-docker-app:latest
    - Downloads the container image from Docker Hub onto any target machine having Docker installed.

Procedure

Step 1: Set up the Project Folder Structure
  Create a directory named 'flask-docker-app' with the following hierarchy:
    flask-docker-app/
    ├── app.py
    ├── requirements.txt
    └── Dockerfile

Step 2: Develop the Flask Web Application (app.py)
  Create 'app.py' and write code to instantiate a Flask app, render an HTML 
  template with styled CSS cards and gradient background, and bind the server 
  to host '0.0.0.0' and port 5000.

Step 3: Define Dependencies (requirements.txt)
  Create 'requirements.txt' and specify the required Flask framework version:
    Flask==2.2.5

Step 4: Create the Dockerfile
  Define container build instructions:
  - FROM python:3.9-slim             (Use minimal Python 3.9 base image)
  - WORKDIR /app                     (Set working directory inside container)
  - COPY requirements.txt .          (Copy dependency manifest)
  - RUN pip install -r requirements.txt (Install required Python packages)
  - COPY . .                         (Copy remaining application source code)
  - EXPOSE 5000                      (Inform Docker that container listens on port 5000)
  - CMD ["python", "app.py"]         (Define entrypoint command to run application)

Step 5: Build the Docker Image
  Open terminal in 'flask-docker-app' and execute:
    docker build -t flask-docker-app .

Step 6: Run and Verify the Container Locally
  Execute:
    docker run -p 5000:5000 flask-docker-app
  Open a web browser and navigate to:
    http://localhost:5000
  Verify that the web application renders successfully.

Step 7: Authenticate with Docker Hub
  Log in to Docker Hub via CLI:
    docker login

Step 8: Tag the Docker Image for Remote Repository
  Tag the local image with your Docker Hub username:
    docker tag flask-docker-app klassy01/flask-docker-app:latest

Step 9: Push the Image to Docker Hub
  Push the image layers to the public registry:
    docker push klassy01/flask-docker-app:latest

Step 10: Test Pull and Run on Any Target Machine
  Verify image distribution by pulling and executing on port 5050:
    docker pull klassy01/flask-docker-app:latest
    docker run -p 5050:5000 klassy01/flask-docker-app:latest
  Open browser at:
    http://localhost:5050

Sample Inputs

[A] app.py

from flask import Flask, render_template_string
app = Flask(__name__)
HTML_TEMPLATE = """
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Flask Docker App</title>
<style>
body {
background: linear-gradient(to right, #00c6ff, #0072ff);
color: white;
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
text-align: center;
padding-top: 100px;
}
h1 {
font-size: 3em;
margin-bottom: 0.2em;
}
p {
font-size: 1.5em;
}
.card {
background: rgba(255, 255, 255, 0.1);
padding: 2em;
border-radius: 20px;
box-shadow: 0 0 20px rgba(0,0,0,0.3);
width: 50%;
margin: auto;
}
</style>
</head>
<body>
<div class="card">
<h1>🐳 Welcome to Flask + Docker!</h1>
<p>This is a vibrant web page running inside a Docker container.</p>
<p>Change the code → Rebuild → Restart Docker to see updates!</p>
</div>
</body>
</html>
"""

@app.route('/')
def home():
    return render_template_string(HTML_TEMPLATE)

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
--------------------------------------------------------------------------------

--- [B] requirements.txt ---
--------------------------------------------------------------------------------
Flask==2.2.5
--------------------------------------------------------------------------------

--- [C] Dockerfile ---
--------------------------------------------------------------------------------
FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "app.py"]

exp 3

Objective

To create a simple Python application and configure a GitHub Actions workflow that automatically runs tests with pytest, builds a Docker image, and pushes the image to Docker Hub, with an optional release tag (v1.0.0).

Tools/ Software Required

Operating System	: Windows 10/11 / Linux / macOS
Programming Language	: Python 3.11+
Testing Framework	: pytest 8.3.2
Version Control	: Git and GitHub account
CI Service	: GitHub Actions
Containerization Tool	: Docker Desktop / Docker Engine (optional locally)
Container Registry	: Docker Hub Account (User: klassy01)
Code Editor	: Visual Studio Code / Any Text Editor

Industry Relevance and Applications

1. Continuous Integration:
Every push and pull request is automatically built and tested, so bugs are found within minutes of being introduced instead of at release time.

2. Automated Quality Gates:
The pipeline pushes the image only if the pytest tests pass, which prevents broken builds from reaching the registry.

3. Standard Build Artifacts:
Docker images tagged with the commit SHA or release version are immutable artifacts that are reused unchanged in testing, staging, and production.

4. Secure Secret Handling:
Registry credentials are kept as encrypted GitHub Secrets and are never stored in the repository, which follows industry security practice.

5. Release Automation:
Pushing a Git tag such as v1.0.0 automatically publishes a versioned image, which supports traceable and repeatable releases.

Description

Continuous Integration (CI) is the practice of automatically building and testing code whenever it changes. In this experiment a small Python application with a pytest test is stored in a GitHub repository. A GitHub Actions workflow checks out the code, installs dependencies, runs the tests, builds a Docker image, logs in to Docker Hub using secrets, and pushes the image with generated tags.

Key Concepts:
- GitHub Actions: GitHub's built-in CI/CD service that runs workflows defined in YAML files.
- Workflow: An automated process defined in .github/workflows/*.yml and started by events such as push or pull request.
- Job and Step: A job runs on a runner (ubuntu-latest) and is made up of ordered steps.
- pytest: A Python testing framework used to run the unit tests.
- Dockerfile: Instructions used to build the container image of the application.
- GitHub Secrets: Encrypted variables (DOCKERHUB_USERNAME, DOCKERHUB_TOKEN) used to store credentials safely.
- Docker Buildx: Docker build tool used by the build-push action.
- Image Tags: Labels such as latest, sha-<commit> and the release tag that identify image versions.
- Docker Hub Access Token: A revocable token used instead of the account password to authenticate pushes.

Command list with explanation

1. mkdir python-ci-docker-lab
    - Creates the project folder.

2. cd python-ci-docker-lab
    - Moves into the project folder.

3. mkdir -p .github/workflows
    - Creates the folder in which GitHub looks for workflow files.
    - Flag '-p' creates parent folders as needed.

4. python app.py
    - Runs the application locally.

5. pytest -q
    - Runs all tests in quiet mode.
    - Flag '-q' reduces the output.

6. docker build -t klassy01/python-ci-lab:local .
    - Builds the Docker image and tags it as 'local'.

7. docker run --rm klassy01/python-ci-lab:local
    - Runs the image and removes the container when it exits.
    - Flag '--rm' deletes the container after it stops.

8. git init
    - Initializes a new local Git repository.

9. git add .
    - Stages all files for commit.

10. git commit -m "init lab"
    - Saves the staged files with the message 'init lab'.

11. git branch -M main
    - Renames the current branch to 'main'.

12. git remote add origin https://github.com/<your-username>/python-ci-docker-lab.git
    - Links the local repository to the GitHub repository.

13. git push -u origin main
    - Pushes the main branch to GitHub and sets it as the upstream branch.
    - This push triggers the workflow.

14. git tag v1.0.0
    - Creates a release tag on the current commit.

15. git push origin v1.0.0
    - Pushes the tag to GitHub, which triggers the workflow and publishes an image tagged v1.0.0.

Procedure

Step 1: Create a New Project Folder
    mkdir python-ci-docker-lab
    cd python-ci-docker-lab

Step 2: Create the Application Files
  Create 'app.py', 'tests/test_app.py', 'requirements.txt', 'Dockerfile', and
  '.gitignore' with the contents given in Sample Inputs.

Step 3: Add the GitHub Actions Workflow
  Create the workflow folder and the workflow file:

    mkdir -p .github/workflows

  Save the workflow as '.github/workflows/ci-dockerhub.yml' (see Sample Inputs).

Step 4: Test Locally (Optional)
    python app.py
    pytest -q

  Build and run the image:
    docker build -t klassy01/python-ci-lab:local .
    docker run --rm klassy01/python-ci-lab:local

Step 5: Initialize Git and Push to GitHub
  Create an empty repository named 'python-ci-docker-lab' on GitHub, then run:

    git init
    git add .
    git commit -m "init lab"
    git branch -M main
    git remote add origin https://github.com/<your-username>/python-ci-docker-lab.git
    git push -u origin main

Step 6: Add GitHub Secrets
  In the repository go to Settings > Secrets and variables > Actions and add:

    DOCKERHUB_USERNAME  : your Docker Hub username
    DOCKERHUB_TOKEN     : Docker Hub access token (Account Settings > Security)

Step 7: Watch the CI Run
  Open the GitHub repository > Actions tab, select the workflow run, and view the logs
  of each step (checkout, tests, login, build and push).

Step 8: Verify the Image on Docker Hub
  Check that the image exists at:

    docker.io/klassy01/python-ci-lab

Step 9: Release with a Tag (Optional)
    git tag v1.0.0
    git push origin v1.0.0

  A new image tagged v1.0.0 is published to Docker Hub.

Sample Inputs

[A] app.py
--------------------------------------------------------------------------------
def add(a, b):
    return a + b

if __name__ == "__main__":
    print("Hello from Python CI Lab!")
    print("2 + 3 =", add(2, 3))
--------------------------------------------------------------------------------

[B] tests/test_app.py
--------------------------------------------------------------------------------
from app import add


def test_add():
    assert add(2, 3) == 5
    assert add(-1, 1) == 0
--------------------------------------------------------------------------------

[C] requirements.txt
--------------------------------------------------------------------------------
pytest==8.3.2
--------------------------------------------------------------------------------

[D] Dockerfile
--------------------------------------------------------------------------------
FROM python:3.11-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .

CMD ["python", "app.py"]
--------------------------------------------------------------------------------

[E] .gitignore
--------------------------------------------------------------------------------
__pycache__/
.venv/
.pytest_cache/
.DS_Store
*.pyc
--------------------------------------------------------------------------------

[F] .github/workflows/ci-dockerhub.yml
--------------------------------------------------------------------------------
name: ci-dockerhub

on:
  push:
    branches: [ "main" ]
    tags: [ "*" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build-test-push:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'

      - name: Install deps
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt

      - name: Run tests
        run: pytest -q

      - name: Docker meta
        id: meta
        uses: docker/metadata-action@v5
        with:
          images: ${{ secrets.DOCKERHUB_USERNAME }}/python-ci-lab
          tags: |
            type=raw,value=latest,enable={{is_default_branch}}
            type=sha,prefix=sha-,format=short
            type=ref,event=tag

      - name: Set up QEMU
        uses: docker/setup-qemu-action@v3

      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v3

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}

      - name: Build and push
        uses: docker/build-push-action@v6
        with:
          context: .
          push: true
          tags: ${{ steps.meta.outputs.tags }}
          labels: ${{ steps.meta.outputs.labels }}
          platforms: linux/amd64
exp 4


Objective

To run Jenkins inside Docker using Docker Compose and to create a Jenkins pipeline that generates a static website, publishes it inside Jenkins using the HTML Publisher plugin, and archives the build artifacts.

Tools/ Software Required

Operating System	: Windows 10/11 / Linux / macOS
Containerization Tool	: Docker Desktop / Docker Engine with Docker Compose
CI/CD Server	: Jenkins (jenkins/jenkins:lts image)
Jenkins Plugin	: HTML Publisher Plugin
Pipeline Language	: Jenkins Declarative Pipeline (Groovy)
Web Technologies	: HTML5, CSS3
Testing Tools	: Web Browser (Chrome / Edge), Terminal / PowerShell

Industry Relevance and Applications

1. Pipeline as Code:
Build and publish steps are written as a Jenkinsfile, so they can be version-controlled, reviewed, and reused in the same way as application code.

2. Jenkins in Containers:
Running Jenkins in Docker gives a disposable, reproducible CI server that can be started anywhere with one command and upgraded by changing the image tag.

3. Automated Website Delivery:
Companies use pipelines to generate and publish documentation sites, reports, and landing pages automatically after every change.

4. Build Artifact Management:
Archiving artifacts keeps every build output available for download, audit, and rollback.

5. Persistent CI Data:
A Docker volume keeps Jenkins jobs, plugins, and settings safe across container restarts and upgrades.

Description

Jenkins is an open-source automation server used for continuous integration and delivery. In this experiment Jenkins runs in a Docker container started with Docker Compose. A pipeline job generates the files of a simple static website (HTML and CSS) in the workspace, publishes it as an HTML report that can be viewed from the build page, and archives the generated site folder as a build artifact.

Key Concepts:
- Jenkins: An automation server that builds, tests, and deploys software using jobs and pipelines.
- Docker Compose: A tool that defines and runs containers from a docker-compose.yml file.
- Docker Volume: Persistent storage (jenkins_home) that keeps Jenkins data outside the container.
- Pipeline: A series of stages, defined as code, that Jenkins runs automatically.
- Stage / Step: A stage is a named phase of the pipeline; steps are the commands inside it.
- writeFile: Pipeline step that creates a file in the workspace from text content.
- HTML Publisher Plugin: Plugin that publishes an HTML folder as a report page linked from the job.
- archiveArtifacts: Pipeline step that stores files from a build so they can be downloaded later.
- Initial Admin Password: One-time password read from the container to unlock Jenkins on first start.

Command list with explanation

1. mkdir ~/jenkins-static-site && cd ~/jenkins-static-site
    - Creates the lab folder and moves into it.

2. docker compose up -d
    - Creates and starts the Jenkins container from docker-compose.yml.
    - Flag '-d' runs it in the background.

3. docker ps
    - Lists running containers; the 'jenkins' container should be running.

4. docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    - Runs a command inside the Jenkins container to display the initial admin password.

5. docker compose logs jenkins
    - Shows the Jenkins logs, which also contain the initial admin password.

6. docker compose down
    - Stops and removes the Jenkins container (the volume with data is kept).

Procedure

Step 1: Create the Lab Folder
    mkdir ~/jenkins-static-site && cd ~/jenkins-static-site

Step 2: Create the docker-compose.yml File
  Create 'docker-compose.yml' with the content given in Sample Inputs.

Step 3: Start Jenkins
    docker compose up -d

Step 4: Get the Initial Admin Password
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword

Step 5: Complete the Jenkins Setup
  Open http://localhost:8080 in a browser, enter the admin password, choose
  'Install suggested plugins', and create the admin user.

Step 6: Install the HTML Publisher Plugin
  Go to Manage Jenkins > Plugins > Available plugins, search for
  'HTML Publisher', install it, and restart Jenkins if prompted.

Step 7: Create the Pipeline Job
  Click New Item, select Pipeline, and name it 'karunya-site-pipeline'.

  Under Pipeline > Definition choose 'Pipeline script', paste the pipeline script given in
  Sample Inputs, and click Save.

Step 8: Run the Pipeline and View the Website
  Click Build Now. After a successful build open the build page and click
  'Karunya University - Simple Site' in the left menu to see the website inside Jenkins.

  Optionally download the archived 'site/' folder from the build page and open index.html locally.

Step 9: Clean Up (Optional)
    docker compose down

Sample Inputs

[A] docker-compose.yml
--------------------------------------------------------------------------------
version: '3.8'

services:
  jenkins:
    image: jenkins/jenkins:lts
    container_name: jenkins
    restart: unless-stopped
    ports:
      - "8080:8080"
      - "50000:50000"
    volumes:
      - jenkins_home:/var/jenkins_home
      - /var/run/docker.sock:/var/run/docker.sock

volumes:
  jenkins_home:
    driver: local
--------------------------------------------------------------------------------

[B] Jenkinsfile (Pipeline script)
--------------------------------------------------------------------------------
pipeline {
  agent any

  stages {
    stage('Generate site') {
      steps {
        script {
          def year = sh(script: 'date +%Y', returnStdout: true).trim()
          sh 'rm -rf site || true'
          sh 'mkdir -p site/assets'

          writeFile file: 'site/index.html', text: """<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1"/>
<title>Karunya University - Simple Site</title>
<link rel="stylesheet" href="assets/style.css"/>
</head>
<body>
<header class="site-header">
<div class="container">
<h1>Karunya University</h1>
<p class="tagline">Values - Knowledge - Service</p>
</div>
</header>

<main class="container">
<section class="card">
<h2>About Karunya University</h2>
<p>Karunya Institute of Technology and Sciences is a leading centre for higher education in India.</p>
</section>
</main>

<footer class="site-footer container">
<p>&copy; ${year} Karunya University - Generated by Jenkins</p>
</footer>
</body>
</html>
"""

          writeFile file: 'site/assets/style.css', text: """
body { font-family: Arial, sans-serif; margin:0; }
.container { max-width:800px; margin:0 auto; padding:20px; }
.site-header { background:#0b3d91; color:#fff; padding:20px; }
.tagline { font-size:14px; opacity:0.8; }
.card { background:#fff; border:1px solid #ddd; padding:15px; margin:15px 0; border-radius:6px; }
.site-footer { text-align:center; font-size:12px; color:#555; margin-top:20px; }
"""
        }
      }
    }

    stage('Publish site') {
      steps {
        publishHTML([
          allowMissing: false,
          alwaysLinkToLastBuild: true,
          keepAll: true,
          reportDir: 'site',
          reportFiles: 'index.html',
          reportName: 'Karunya University - Simple Site'
        ])
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'site/**', fingerprint: true
    }
  }
}

exp 6



Objective

To install and configure the Kubernetes tool chain (Docker, kubectl and Minikube) and to manage basic Kubernetes resources using the kubectl command-line interface by creating Pods and Deployments, scaling applications, performing rolling updates and rollbacks, exposing a Deployment as a Service, and cleaning up resources.

Tools/ Software Required

Operating System	: Windows 10/11 / Ubuntu / Debian Linux / macOS
Hardware	: Minimum 4 GB RAM, internet access
Container Runtime	: Docker Desktop (WSL2 backend) / Docker Engine
Kubernetes CLI	: kubectl (kubernetes-cli)
Local Cluster	: Minikube (single-node cluster, Docker driver)
Package Manager	: Chocolatey (Windows)
Container Image	: nginx:latest / nginx:1.25
Testing Tools	: Web Browser (Chrome / Edge), PowerShell / CMD

Industry Relevance and Applications

1. Container Orchestration at Scale:
Kubernetes is the industry-standard platform for automating deployment, scaling, and management of containerized applications across clusters of machines.

2. Self-Healing and High Availability:
Deployments continuously maintain the desired number of replicas, automatically restarting failed Pods and rescheduling them to healthy nodes.

3. Zero-Downtime Releases:
Rolling updates and instant rollbacks (kubectl rollout) allow new application versions to be released, and faulty ones reverted, without service interruption.

4. Declarative Infrastructure and GitOps:
YAML manifests applied with kubectl describe the desired state of applications and can be version-controlled and automated in CI/CD pipelines (GitHub Actions, Jenkins, Argo CD).

5. Multi-Cloud and Cloud-Native Portability:
The same kubectl workflow works on Minikube, Amazon EKS, Azure AKS, and Google GKE, making Kubernetes skills directly transferable across cloud providers.

Description

Kubernetes (K8s) is an open-source container orchestration system that schedules and manages containers across a cluster. kubectl is its command-line tool for communicating with the cluster API server, and Minikube provides a local single-node cluster that runs inside Docker for learning and testing.

Key Concepts:
- Cluster / Node: A set of machines (nodes) that run containerized workloads; Minikube creates a single-node cluster.
- Pod: The smallest deployable unit in Kubernetes; wraps one or more containers sharing network and storage.
- Deployment: A controller that manages a set of identical Pods (ReplicaSet), enabling scaling, rolling updates, and rollbacks.
- ReplicaSet: Ensures a specified number of Pod replicas are running at any given time.
- Service: A stable network endpoint that exposes a set of Pods; types include ClusterIP, NodePort, and LoadBalancer.
- NodePort: A Service type that exposes the application on a static port of each cluster node.
- Labels and Selectors: Key-value tags (e.g., app: nginx) used to group and select resources such as Pods.
- Manifest (YAML): A declarative file describing the desired state of a Kubernetes resource.
- kubectl: CLI used to create, inspect, update, and delete Kubernetes resources.
- Minikube: Tool that runs a local Kubernetes cluster for development and learning.

Command list with explanation

1. docker --version
    - Displays the installed Docker version; confirms Docker is installed correctly.

2. choco install kubernetes-cli
    - Installs kubectl on Windows using the Chocolatey package manager.

3. kubectl version --client
    - Verifies the kubectl installation by printing the client version.

4. choco install minikube
    - Installs Minikube on Windows using Chocolatey.

5. minikube start --driver=docker
    - Creates and starts a local single-node Kubernetes cluster.
    - Flag '--driver=docker' runs the cluster inside a Docker container.

6. minikube status
    - Shows the status of the Minikube host, kubelet, API server, and kubeconfig.

7. kubectl get nodes
    - Lists cluster nodes; a node in 'Ready' state confirms the cluster is working.

8. kubectl apply -f nginx-pod.yaml
    - Creates or updates resources defined in the manifest file.
    - Flag '-f' specifies the YAML file to apply.

9. kubectl get pods
    - Lists Pods in the current namespace with their READY, STATUS, RESTARTS, and AGE.

10. kubectl describe pod nginx-pod
    - Shows detailed information about a Pod, including its node, IP, containers, and events.

11. kubectl port-forward pod/nginx-pod 8080:80
    - Forwards local port 8080 to port 80 of the Pod so it can be accessed in a browser.

12. kubectl delete pod nginx-pod
    - Deletes the specified Pod from the cluster.

13. kubectl create deployment my-nginx --image=nginx
    - Creates a Deployment named 'my-nginx' that runs the nginx image.

14. kubectl get deployments
    - Lists Deployments with their desired, current, and available replica counts.

15. kubectl get pods -l app=my-nginx
    - Lists only the Pods matching the label selector 'app=my-nginx'.

16. kubectl scale deployment my-nginx --replicas=3
    - Changes the number of Pod replicas of the Deployment to 3.

17. kubectl set image deployment/my-nginx nginx=nginx:1.25
    - Updates the container image, triggering a rolling update of the Pods.

18. kubectl rollout status deployment/my-nginx
    - Watches the progress of the rolling update until it completes.

19. kubectl rollout undo deployment/my-nginx
    - Rolls the Deployment back to its previous revision if the update fails.

20. kubectl expose deployment my-nginx --type=NodePort --port=80
    - Creates a Service that exposes the Deployment outside the cluster.
    - Flag '--type=NodePort' opens a static port on the node; '--port=80' is the Service port.

21. kubectl get svc
    - Lists Services with their type, cluster IP, and assigned NodePort.

22. minikube service my-nginx --url
    - Prints the URL used to access the NodePort Service from the host machine.

23. kubectl delete svc my-nginx
    - Deletes the Service named 'my-nginx'.

24. kubectl delete deployment my-nginx
    - Deletes the Deployment and the Pods it manages.

25. kubectl delete all --all -n default
    - Deletes all resources in the 'default' namespace.
    - Flag '--all' selects every resource; '-n default' selects the namespace.

26. minikube stop
    - Stops the running local cluster without deleting it.

27. minikube delete
    - Permanently deletes the local cluster and its associated resources.

Procedure

Step 1: Install Docker
  Download and install Docker Desktop from Docker's website, enable the WSL2 backend,
  start Docker Desktop, and verify the installation:

    docker --version

Step 2: Install kubectl (Kubernetes CLI)
  Open PowerShell as Administrator and install kubectl using Chocolatey:

    choco install kubernetes-cli

  Verify the installation:
    kubectl version --client

Step 3: Install and Start Minikube
  Install Minikube and start the cluster using the Docker driver:

    choco install minikube
    minikube start --driver=docker

  Verify that the cluster is running:
    minikube status
    kubectl get nodes
  The node must be in 'Ready' state before proceeding.

Step 4: Create a Simple Pod
  Create a file named 'nginx-pod.yaml' (see Sample Inputs) and apply the manifest:

    kubectl apply -f nginx-pod.yaml

  Check the Pod status (expected: nginx-pod 1/1 Running):
    kubectl get pods

  View detailed information about the Pod:
    kubectl describe pod nginx-pod

  Forward a local port to access the Pod:
    kubectl port-forward pod/nginx-pod 8080:80

  Open http://localhost:8080 in a browser to view the nginx welcome page.

  Press Ctrl+C to stop port-forwarding, then delete the Pod:
    kubectl delete pod nginx-pod

Step 5: Create a Deployment and Scale It
  Create a Deployment and verify the Deployment and its Pods:

    kubectl create deployment my-nginx --image=nginx
    kubectl get deployments
    kubectl get pods -l app=my-nginx

  Scale the Deployment to 3 replicas:

    kubectl scale deployment my-nginx --replicas=3
    kubectl get pods

Step 6: Perform a Rolling Update and Rollback
  Update the container image to a specific version:

    kubectl set image deployment/my-nginx nginx=nginx:1.25
    kubectl rollout status deployment/my-nginx

  If something goes wrong, roll back to the previous revision:
    kubectl rollout undo deployment/my-nginx

Step 7: Expose the Deployment as a Service
  Expose the Deployment using a NodePort Service and check it:

    kubectl expose deployment my-nginx --type=NodePort --port=80
    kubectl get svc

  Get the application URL from Minikube and open it in a browser:
    minikube service my-nginx --url

  To remove the Service:
    kubectl delete svc my-nginx

Step 8: Clean Up Resources
  Delete all resources created during the experiment:

    kubectl delete deployment my-nginx
    kubectl delete svc my-nginx
    kubectl delete all --all -n default

Step 9: Stop or Delete the Cluster (Optional)
  Stop the cluster, or delete it completely:

    minikube stop
    minikube delete

Sample Inputs

[A] nginx-pod.yaml

apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    app: nginx
spec:
  containers:
  - name: nginx
    image: nginx:latest
    ports:
    - containerPort: 80
--------------------------------------------------------------------------------

--- [B] Quick Command Reference ---
--------------------------------------------------------------------------------
kubectl create deployment my-nginx --image=nginx
kubectl scale deployment my-nginx --replicas=3
kubectl set image deployment/my-nginx nginx=nginx:1.25
kubectl expose deployment my-nginx --type=NodePort --port=80
--------------------------------------------------------------------------------
exp 7

Objective

To deploy a Python web application stored as a public image on Docker Hub to a Kubernetes cluster using a Deployment and a NodePort Service, and to access the running application through Minikube.

Tools/ Software Required

Operating System	: Windows 10/11 / Linux / macOS
Container Runtime	: Docker Desktop / Docker Engine
Kubernetes CLI	: kubectl
Local Cluster	: Minikube (Docker driver)
Container Registry	: Docker Hub (public image dockersamples/flaskapp)
Code Editor	: Visual Studio Code / Any Text Editor
Testing Tools	: Web Browser (Chrome / Edge), PowerShell / CMD

Industry Relevance and Applications

1. Registry-Driven Deployments:
Production clusters pull ready-made images from registries such as Docker Hub, AWS ECR, or Google Artifact Registry, so the same tested image is promoted unchanged from development to production.

2. Declarative Application Management:
Deployment and Service YAML files describe the desired state of an application. They are stored in Git and applied by CI/CD or GitOps tools, giving repeatable and auditable releases.

3. High Availability through Replicas:
A Deployment keeps multiple replicas of a Python web service running and automatically replaces failed Pods, which keeps customer-facing APIs available.

4. Service Discovery and Load Balancing:
A Kubernetes Service gives a group of Pods one stable address and spreads incoming traffic across them, removing the need for manual load balancer configuration.

5. Cloud-Native Portability:
The same manifests run on Minikube, Amazon EKS, Azure AKS, and Google GKE, so skills and configurations transfer directly between local and cloud environments.

Description

This experiment deploys a containerized Python (Flask) web application, already published on Docker Hub, to a local Minikube cluster. A Deployment manages two replicas of the application, and a NodePort Service exposes it outside the cluster so that it can be opened in a browser.

Key Concepts:
- Docker Hub: A public registry from which Kubernetes nodes pull container images.
- Deployment: A controller that creates and maintains the desired number of identical Pods and handles updates.
- Replicas: The number of identical Pod copies the Deployment keeps running (2 in this experiment).
- Labels and Selectors: Key-value tags (app: python-web) that let a Deployment and a Service find their Pods.
- containerPort: The port on which the application listens inside the container (5000).
- Service (NodePort): Exposes the Pods on a static port of the node so the app is reachable from outside the cluster.
- targetPort: The container port to which the Service forwards traffic.
- Minikube Service URL: Command that prints the host URL and port that maps to the NodePort Service.

Command list with explanation

1. minikube start --driver=docker
    - Starts a local single-node Kubernetes cluster inside Docker.

2. kubectl get nodes
    - Lists the cluster nodes; the node must be in 'Ready' state.

3. docker pull dockersamples/flaskapp
    - Downloads the Python web app image from Docker Hub to verify registry access.

4. kubectl apply -f python-deployment.yaml
    - Creates or updates the Deployment defined in the manifest.
    - Flag '-f' specifies the YAML file.

5. kubectl get deployments
    - Lists Deployments with their READY, UP-TO-DATE, and AVAILABLE counts.

6. kubectl get pods
    - Lists the Pods created by the Deployment and their status.

7. kubectl describe deployment python-web-deployment
    - Shows detailed information about the Deployment: replicas, image, strategy, and events.

8. kubectl apply -f python-service.yaml
    - Creates the NodePort Service that exposes the Pods.

9. kubectl get svc
    - Lists Services with their type, cluster IP, and node port.

10. minikube service python-web-service --url
    - Prints the URL used to open the Service in a browser.

11. kubectl delete svc python-web-service
    - Deletes the Service.

12. kubectl delete deployment python-web-deployment
    - Deletes the Deployment and its Pods.

13. minikube stop
    - Stops the running cluster without deleting it.

14. minikube delete
    - Permanently deletes the local cluster.

Procedure

Step 1: Verify the Cluster
  Start Minikube and confirm the node is Ready:

    minikube start --driver=docker
    kubectl get nodes

Step 2: Choose the Python Docker Image
  Use the public sample image hosted on Docker Hub and verify that it can be pulled:

    docker pull dockersamples/flaskapp

Step 3: Create the Kubernetes Deployment
  Create 'python-deployment.yaml' (see Sample Inputs) and apply it:

    kubectl apply -f python-deployment.yaml

  Check the status:
    kubectl get deployments
    kubectl get pods

  View the details:
    kubectl describe deployment python-web-deployment

Step 4: Expose the Deployment as a Service
  Create 'python-service.yaml' (see Sample Inputs) and apply it:

    kubectl apply -f python-service.yaml

  Check that the Service is created:
    kubectl get svc

Step 5: Access the Application
  Get the URL from Minikube and open it in a browser:

    minikube service python-web-service --url

  The Python web app page should be displayed.

Step 6: Clean Up Resources
  Delete the Service and the Deployment:

    kubectl delete svc python-web-service
    kubectl delete deployment python-web-deployment

  Optionally stop or delete the cluster:
    minikube stop
    minikube delete

Sample Inputs

[A] python-deployment.yaml
--------------------------------------------------------------------------------
apiVersion: apps/v1
kind: Deployment
metadata:
  name: python-web-deployment
  labels:
    app: python-web
spec:
  replicas: 2
  selector:
    matchLabels:
      app: python-web
  template:
    metadata:
      labels:
        app: python-web
    spec:
      containers:
      - name: python-web
        image: dockersamples/flaskapp:latest
        ports:
        - containerPort: 5000
--------------------------------------------------------------------------------
[B] python-service.yaml
--------------------------------------------------------------------------------
apiVersion: v1
kind: Service
metadata:
  name: python-web-service
spec:
  type: NodePort
  selector:
    app: python-web
  ports:
    - protocol: TCP
      port: 5000
      targetPort: 5000

