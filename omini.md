# Deploying React App on Windows Server using Docker & Docker Compose

## **1. Install Docker on Windows Server**

### **Step 1: Enable Windows Features for Docker**
Open **PowerShell as Administrator** and run:
```powershell
wsl --install
```
This enables **WSL2 (Windows Subsystem for Linux)**, required for Docker.

### **Step 2: Install Docker**
Download and install Docker using PowerShell:
```powershell
Invoke-WebRequest -Uri https://desktop.docker.com/win/main/amd64/DockerDesktopInstaller.exe -OutFile DockerDesktopInstaller.exe
Start-Process -Wait -FilePath .\DockerDesktopInstaller.exe
```
After installation, **restart your system**.

### **Step 3: Verify Docker Installation**
Run:
```powershell
docker --version
```
Expected output:
```
Docker version 24.x.x, build xxxxxxx
```

---

## **2. Install Docker Compose**
Docker Compose is included in Docker Desktop. However, if using **Docker Engine**, install it manually:

```powershell
Invoke-WebRequest "https://github.com/docker/compose/releases/latest/download/docker-compose-windows-x86_64.exe" -OutFile "C:\Program Files\Docker\docker-compose.exe"
```

Verify the installation:
```powershell
docker-compose --version
```
Expected output:
```
Docker Compose version v2.x.x
```

---

## **3. Clone Your GitHub Repository on Windows Server**

First, install **Git** if not installed:
```powershell
winget install --id Git.Git -e --source winget
```

Then, clone your repository:
```powershell
git clone https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPO.git
```
Navigate to the project folder:
```powershell
cd YOUR_REPO
```

---

## **4. Run Docker Compose**

### **Step 1: Build and Run the Containers**
Run the following command inside your project directory:
```powershell
docker-compose up -d --build

docker ps
```
You should see your **React app container** running.

---

## **5. Access Your React App**

- Open a browser and go to:
  **`http://serverip:3000`**  
  (Replace `localhost` with your Windows Server's IP if accessing remotely)

---



