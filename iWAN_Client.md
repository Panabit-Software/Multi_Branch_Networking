<a name="readme-top"></a>
<h1 align="center">
  <img src="assets/Panabit.png" alt="Panabit" width="240" height="72">
  <br>
  Panabit Smart Application Gateway
</h1>
<h4 align="center">Integrated Intelligent Application Gateway</h4>

<p align="center">
  <a href="iWAN_Client_CN.md" style="color: #007bff; text-decoration: none; font-weight: bold;">中文</a> | <span style="color: #007bff; font-weight: bold;">English</span>
</p>

---

# 🚀 **Panabit SD-WAN Client Officially Released!**

🔹 Panabit **SD-WAN** was previously used mainly for **site-to-site VPN connectivity**, requiring Panabit devices on both ends.  
🔹 Now, the **brand-new** Windows and Linux clients are available, allowing computers to **connect to the SD-WAN network directly!**  

📥 **Download Link**: [👉 Click to Download](https://www.panabit.com/download)  

> 📝 **Note**: Both Windows and Linux versions are included in the package.

---

## 📌 **Table of Contents**
1. [🖥 Windows Deployment](#-windows-deployment)
2. [🐧 Linux Deployment](#-linux-deployment)
   - [📂 Create Configuration Directory](#-create-configuration-directory)
   - [⚙️ Create Configuration File](#-create-configuration-file)
   - [📤 Upload the Program](#-upload-the-program)
   - [🔑 Grant Execution Permission](#-grant-execution-permission)
   - [▶️ Run the Program](#-run-the-program)
   - [🔍 Verify iwan0 Interface](#-verify-iwan0-interface)
   - [🚦 Add Static Route](#-add-static-route)

---

## 🖥 **Windows Deployment**
Extract the package and **double-click iWAN.exe** to run it.

| Configuration | Description |
|-------------|-------------|
| **Server** | IP address or domain name of the iWAN server |
| **Port** | Port number mapped by the iWAN server |
| **Username** | Login username for iWAN |
| **Password** | Corresponding password for the username |

---

## 🐧 **Linux Deployment**

### 📂 **Create Configuration Directory**

Before running the program, you need to **manually configure the server information**.  
Use the following commands to **create the /etc/sdwan directory**:
```bash
sudo mkdir /etc/sdwan
sudo vim /etc/sdwan/iwan.conf
```

### 📂 **Create Configuration File**

```bash
[iwan0]
server=server_ip
username=your_username
password=your_password
port=server_port
mtu=maximum_transmission_unit
encrypt=Encryption (0 for no encryption, 1 for encryption)
```

### 📤 **Upload the Program**

Use the `scp` tool to upload the file to the server.

### 🔑 **Grant Execution Permission**

```bash
chmod +x /root/sdwand
```

### ▶️ **Run the Program**

```bash
/root/sdwand &
```

###  🔍 **Verify iwan0 Interface**

Run `ifconfig` to check the added `iwan0` interface, which will be automatically assigned an IP address.

###  🚦 **Add Static Route**

Add a static route for the iWAN network segment:

```bash
route add –net x.x.x.x/nn dev iwan0
```

---

📢 **More Information**  
🔗 Visit our website: [www.panabit.com](https://www.panabit.com/)  
🔗 Join our forum: [bbs.panabit.com](https://bbs.panabit.com/)  
🔗 Technical support email: support@panabit.com  

📞 Contact us for more detailed solutions!



