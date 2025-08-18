---
title: VirtualBox Kali Linux
tags:
  - linux
  - virtualization
  - kalilinux
---
There are many ways to operate kali linux. You can you virtual machine (VirtualBox, VmWare, etc) or you can dual boot your system. In this article, we will be Installing our Kali linux as virtual machine using VirtualBox (Oracle).

Here is a **step-by-step guide to installing Kali Linux on VirtualBox**:

# Step 1: Download VirtualBox (Oracle)

1. Open Virtual Box Website : [https://www.virtualbox.org/](https://www.virtualbox.org/)

2. Click the Download Button

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*7Qt-pNQes4WstnpU_96bXQ.png)

3. Under VirtualBox Platform Packages, click on “Windows hosts’ if you have windows system or on “macOS” if you have mac. (As per your computer)

4. Also under VirtualBox Extension Pack, click on “Accept and download”

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*jycg59UwuROLrps_EmdCZg.png)

![](https://miro.medium.com/v2/resize:fit:720/1*Rxj2UGsWxohl5H4mcIFkyg.png)

5. Click on .exe file and follow along the installation

# Step 2: Download Kali Linux ISO

1. Open Kali Linux Official Website: [https://www.kali.org/](https://www.kali.org/)

2. Click on **Download**

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*sFCGyFmrp7hXySTm9uKFmw.png)

3. Click on “Recommended” under **Virtual Machine**

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*bb2xddBG8V9_2ClRO9K-Ww.png)

4. Download the folder under **VirtualBox**

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*Pl9Da1_swmaudpRjttogCQ.png)

5. A zip file will be downloaded. Extract the contents of that folder.

![](https://miro.medium.com/v2/resize:fit:695/1*vqZqYEosiVtTg3B8JnqjyA.png)

# Step 3: Open Kali Linux in Virtual Machine

1. Open Virtual Box Interface

2. Click on “**Add**”

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*bMzSD1W858VxfCJ4C-wLnQ.png)

3. Select the Kali linux Virtual Machine from the extracted folder

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*3pMJVO81LwiRgsJw4gE92w.png)

![](https://miro.medium.com/v2/resize:fit:624/1*rDh4lPLmnZ16O7AOfMDGIg.png)

# Step 4: Configure Kali Linux VM

1. Open “Settings”

Press enter or click to view image in full size

![](https://miro.medium.com/v2/resize:fit:1050/1*3qvQcAfP4E_4DsWewWSV8Q.png)

2. Go to System. Here you can configure how much power you want to give to your VM. You can change the RAM, Number of cores, etc according to your need

# Step 5: Start the Kali Linux VM

1. Now click on **Start**

2. After the system has booted, a login page would appear. Enter its default credentials. You can later change those credentials

```
Username: kali
Password: kali
```

# Step 6: Update and Upgrade Kali Linux VM

Open your terminal and enter this command

```bash
sudo apt update
```

```bash
sudo apt upgrade
```

