# DevOps Lab 2

## Name: Deepanshu Kumar Jindal  
**SAP ID:** 500105244  
**Roll Number:** R2142220475  
**Batch:** Full Stack AI B1 Hons  

## Installing WSL (Windows Subsystem for Linux)

WSL allows you to run Linux on Windows without a virtual machine. Below is a step-by-step guide to installing WSL on Windows.

---

## **Enable WSL**

1. Open **PowerShell** as Administrator.
2. Run the following command to enable WSL:
   ```sh
   wsl --install
   ```
3. Restart your computer after installation.

---

## **Check Installed WSL Version**  
Run the command to check which version of WSL is installed:  
```sh
wsl --list --verbose
```
If WSL 2 is not installed, update it using:  
```sh
wsl --update
```

---

## **Install a Linux Distribution**  

1. Run the following command to see available Linux distributions:
   ```sh
   wsl --list --online
   ```
2. Install Ubuntu distribution:
   ```sh
   wsl --install -d Ubuntu
   ```
3. Open **Ubuntu** (or the chosen distro) from the Start menu.
4. Set up a username and password when prompted.

---

## **Set WSL Version**  
To ensure using WSL 2, set the default version:  
```sh
wsl --set-default-version 2
```
To check and change the version for a specific distro:  
```sh
wsl --set-version Ubuntu 2
```

---

## **Step 5: Update WSL Kernel (If Needed)**  

If you get an error about WSL 2 requiring an update, download and install the kernel update from Microsoft:  
[WSL Kernel Update](https://aka.ms/wsl2kernel)

---

## **Step 6: Running Linux Commands in WSL**

Once WSL is installed, you can use Linux commands directly from 
- The **WSL terminal** (`Ubuntu` or chosen distro)
- **Windows Terminal**
- **PowerShell** or **Command Prompt** (using `wsl` prefix)
  ```sh
  wsl ls -la
  ```

---

## **Step 7: Accessing Windows Files in WSL**
Your Windows files can be accessed from WSL under `/mnt/c/`.
```sh
cd /mnt/c/Users/DeepanshuJindal
ls
```
---
