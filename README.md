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
<p>- The default webpage will be showing now that we installed ISS. Without IIS enbled, if we went to 127.0.0.1, the "Hmmm... can't reach this page" message would appear. </p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT10" src="https://github.com/user-attachments/assets/1f2a869f-505a-4577-968b-4ad9029d467f" />
    </td>
    <td>
      <img width="1000" alt="OT11" src="https://github.com/user-attachments/assets/067ae469-328b-43ac-baf6-ef86e4bfcd2c" />
    </td>
  </tr>
</table>
<p>- Now that we've got the web server going, its time to start installing evrything we need for osTicket. We'll start with PHP Manager for IIS. PHP is a backend web server language and osTicket basically runs on PHP. </p>
<p>- Open the osTicket-Installation-Files and install PHP Manager for IIS. (PHPManagerForIIS_V1.5.0) </p>
<p>- Let the Installer do it's thing. Agree, click Next, and Yes on eveything.</p>
<p>- Next, install the Rewrite Module. (rewrite_amd64_en-US.msi) Agree and click Next to everything.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT12" src="https://github.com/user-attachments/assets/ae666c73-a7ef-48c5-9518-47c8a22e5c1c" />
    </td>
    <td>
      <img width="1000" alt="OT13" src="https://github.com/user-attachments/assets/623964cf-0bb2-4ff1-8c57-d669e676135c" />
    </td>
  </tr>
</table>
<p>- Create a directory on the C drive called PHP. </p>
<p>- Navigate to Windows(C:) via File Explorer and create a new folder named "PHP". </p>
<p>- Back to the osTicket Installation Files, right-click the (php-7.3.8-nts-Win32-VC15-x86) file and select Extrat All...</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT14" src="https://github.com/user-attachments/assets/0efbd85d-8f29-4e54-8ae5-f433053f926a" />
    </td>
    <td>
      <img width="1000" alt="OT15" src="https://github.com/user-attachments/assets/1f354857-d088-408d-a75b-b67e995db66b" />
    </td>
  </tr>
</table>
<p>- Instead of just extracting right away, click Browse, navigate to Windows(C:), and select the new PHP folder we just created.</p>
<p>- Confirm the Destination and click Extract. After its finished, you can open the PHP folder and see all the PHP files we just installed for osTicket.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT16" src="https://github.com/user-attachments/assets/9231bade-a226-4d7d-b1cf-fe8c3b3eaea9" />
    </td>
    <td>
      <img width="1000" alt="OT17" src="https://github.com/user-attachments/assets/47a41d2f-ec6e-4d42-a806-0075137c61e0" />
    </td>
  </tr>
</table>
<p>- Now, back to the osTicket Installation Files and install a couple more files.</p>
<p>- From osTicket-Installation-Files, install the VC Redistributable file (VC_redist.86). Click Yes and let it do it's thing.</p>
<p>- Next, we'll install MySQL 5.5.62. MySQL is a database that osTicket is going to use to store all of our data. The data will be all the user accounts, ticketing information, and everything we do in osTicket. This will all be stored in the database on the backend. </p>
<p>- Download (mysql-5.5.62-win32)</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT18" src="https://github.com/user-attachments/assets/b0e4f2ed-328b-4db6-9ee2-ad2c1f02b72b" />
    </td>
    <td>
      <img width="1000" alt="OT19" src="https://github.com/user-attachments/assets/8cd4289a-ab6e-4e84-893b-0acb823f726e" />
    </td>
  </tr>
</table>
<p>- Now, back to the osTicket Installation Files and install a couple more files.</p>
<p>- From osTicket-Installation-Files, install the VC Redistributable file (VC_redist.86). Click Yes and let it do it's thing.</p>
<p>- Next, we'll install MySQL 5.5.62. MySQL is a database that osTicket is going to use to store all of our data. The data will be all the user accounts, ticketing information, and everything we do in osTicket. This will all be stored in the database on the backend. </p>
<p>- Download (mysql-5.5.62-win32)</p>
<br/>



