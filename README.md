<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>List of Prerequisites</h2>

- [osTicket Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) (For reference purposes. Link to download zip file is below.)
- [Creating Virtual Machines in the Cloud](https://github.com/joshuaheck1/VM-creation)
- Microsoft Azure (Virtual Machines/Compute)  
- Windows App for macOS
- Remote Desktop

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop / Windows App (macOS)
- Internet Information Services (IIS)
- MySQL
- osTicket

<h2>Operating Systems Used </h2>

- macOS Sequoia
- Windows 10</b> (21H2)

<h2>Installation Steps</h2>

<img width="800" alt="OT2" src="https://github.com/user-attachments/assets/1bd02ffe-5a62-42a9-a1fc-f3a7d09a3de4" />


- In Azure, create a VM with the same configurations as before and name it osTicket-vm. You can refer back to this previous project if needed:
[Creating Virtual Machines in the Cloud](https://github.com/joshuaheck1/VM-creation)

- [osTicket Installation Files](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0) 

<p>- Log in to the osTicket-vm, copy the osTicket Installation Files link above, and paste it into the browser. This will take you to the zip file containing what we need to install osTicket to the VM.</p>
<p>- Yes, it is a large file but click Download anyway.</p>
<p>- Don't "Open file" instead click the folder icon to open the file where it is. Downloads.</p>
 <br/>

<img width="800" alt="OT3" src="https://github.com/user-attachments/assets/41493ab6-9f85-4142-9124-c2d8f108f22f" />

<p>- From Downloads, drag the zip file to the deskstop.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT4" src="https://github.com/user-attachments/assets/146f985b-d0b3-481f-aff2-eb1d85845cdb" />
    </td>
    <td>
      <img width="1000" alt=<"OT5" src="https://github.com/user-attachments/assets/8315b55b-6b12-4cb3-8c18-25d014fc821d" />
    </td>
  </tr>
</table>
<p>- Right-click the folder and select Extract All...</p>
<p>- Confirm the correct destination (Desktop) and click Extract. The folder should be called "osTicket-Installation-Files"</p>
<p>- Once the folder is finished extracting, you may have to minimize a window to see it. It should appear by the Browser icon on the Desktop.</p>
<p>- We will use the files in this folder to install osTicket. I moved the install folder to the top right of my screen (for easy locate) and moved the zip file to a bottom corner to ignore for the rest of the lab. This was to prevent mixing them up because its about to get saucy. 😏 (You can move the zip file to the recycle bin. I didn't realize that til later in the lab.)</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" height="250" alt="OT6" src="https://github.com/user-attachments/assets/433aeaa6-dc4b-4cbb-9456-9e3cff806dcd" />
    </td>
    <td>
      <img width="1000" height="250" alt="OT7" src="https://github.com/user-attachments/assets/28980f89-23d1-4d4f-b963-2379a369dc33" />
    </td>
  </tr>
</table>
<p>- Now we're going to enable IIS (Internet Information Services) within Windows and ensure CGI is installed as well.</p>
<p>- From the Start Menu, go to Control Panel and click Uninstall a program.</p>
<p>- Next, click Turn Windows features on or off. You'll probably want to expand the window that opens.</p>
<br/>


<table>
  <tr>
    <td>
      <img width="1000" alt="OT8" src="https://github.com/user-attachments/assets/3ea9dc16-d359-4f79-8f2a-19506f13107f" />
    </td>
    <td>
      <img width="1000" alt="OT9" src="https://github.com/user-attachments/assets/1641f3d0-ccff-40e2-8e03-856e3d5b17ff" />
    </td>
  </tr>
</table>
<p>- In Windows Features, enable Internet Information Services by clicking the box and then expand -> expand World Wide Web Services -> expand Application Development Features.</p>
<p>- Check the box next to CGI and click OK. Let the install do it's thing and click Finish once it completes. </p>
<p>- Jump over to the Browser and enter 127.0.0.1</p>
<p>- The default webpage will be showing now that we installed ISS. Without ISS enbled, if we went to 127.0.0.1, the "Hmmm... can't reach this page" message would appear. </p>
<br/>
