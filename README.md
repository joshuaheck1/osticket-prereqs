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

<img width="750" alt="OT2" src="https://github.com/user-attachments/assets/1bd02ffe-5a62-42a9-a1fc-f3a7d09a3de4" />


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
<p>- Run the installer for MySQL. Choose "Typical" for Setup Type and click Next. See Figure 17 </p>
<p>- Once Install is complete, check the box next to "Launch the MySQL Instance Configuration Wizard", and click Finish.</p>
</p>- Click Next to start the configuration wizard.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT20" src="https://github.com/user-attachments/assets/67164ce9-a990-4cf0-8c9e-4fbf926dcce6" />
    </td>
    <td>
      <img width="1000" alt="OT21" src="https://github.com/user-attachments/assets/55f3d36b-e17c-41dc-8fbc-e2d9f41d9f23" />
    </td>
  </tr>
</table>
<p>- Select "Standard Configuration", and click Next. See Figure 19</p>
<p>- We'll leave the next options alone and hit Next as shown in Figure 20.</p>
<br/>

<img width="600" alt="OT22" src="https://github.com/user-attachments/assets/ee7d67a1-c2d8-4be9-af92-45a13a4f972c" />

<p>- Okay, we've done a lot of jumping from folder to folder and changing windows to this point. Stand up, stretch, get something to drink, and maybe a snack so we can get locked in. This next step is beyond SUPER IMPORTANT! Absolutely DO NOT MESS THIS UP! (No Pressure) 😏</p>
<p>- Just type the word ROOT in both boxes. Yes, ROOT in all caps. </p>
<p>- Later on, the username will be root but the password is ROOT. This would be really bad in the real world but we're keeping simple for this project. A ton of people struggled with this part in the lab. The huge issue is we won't know its wrong until the end when osTicket fails to launch. </p>
<p>- Click Next, Execute on the next screen, and then Finish.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT23" src="https://github.com/user-attachments/assets/9713df38-bb52-4b7a-b5ec-1bf21f3302ec" />
    </td>
    <td>
      <img width="1000" alt="OT24" src="https://github.com/user-attachments/assets/8cfd5c58-0513-4465-862b-ca9078059580" />
    </td>
  </tr>
</table>
<p>- Now that the scary part is over, we are going to Register PHP from within IIS. Open IIS as an Admin from the Start Menu.</p>
<p>- In IIS, open PHP Manager by double-clicking the icon.</p>
<p>- Click "Register new PHP version", then click the three dots, and browse to the C drive. Windows(C:). </p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT25" src="https://github.com/user-attachments/assets/918df4c8-2c52-4f02-a6c3-9cfa40046631" />
    </td>
    <td>
      <img width="1000" alt="OT26" src="https://github.com/user-attachments/assets/8777aa50-74e6-4c60-b5f7-f9adca31fb95" />
    </td>
  </tr>
</table>
<p>- Select PHP and click Open.</p>
<p>- In PHP, select php-cgi, click Open, and then OK.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT27" src="https://github.com/user-attachments/assets/048674f6-3ed7-42cc-b11b-2610149f683f" />
    </td>
    <td>
      <img width="1000" alt="OT37" src="https://github.com/user-attachments/assets/8a0ef05c-1589-4359-8ac2-a62ab43ad511" />
    </td>
  </tr>
</table>
<p>- We need to reload IIS for the PHP registration to take effect.</p>
<p>- Right-click osTicket-vm in the top-left of IIS and select Stop. You should see a green animation slide across the top bar. </p>
<p>- Give it a couple seconds. Then, right-click osTicket-vm again and select Start. (You can use the Action buttons on the right side of IIS as well).</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT28" src="https://github.com/user-attachments/assets/fb5dfacd-98f9-4cce-bbe9-106cc942c442" />
    </td>
    <td>
      <img width="1000" alt="OT29" src="https://github.com/user-attachments/assets/c377e374-99c6-4d8c-99a0-ba212b3d8fba" />
    </td>
  </tr>
</table>
<p>- Now run back to the osTicket Installation Files folder on the Desktop.🏃‍♂️‍➡️ We need to unzip (osTicket-v1.15.8.zip).</p>
<p>- Right-click osTicket-v1.15.8.zip and select Extract... </p>
<p>- Go ahead and extract the files into the osTicket-Installation-Files folder. You'll notice the new folder at the top. See Figure 28</p>
<br/>

<img width="600" alt="OT30" src="https://github.com/user-attachments/assets/dbd3243f-71e4-4150-b6f0-fa3eeb10bdbf" />

<p>- When it finishes extracting the files, double-click the new osTicket-v1.15.8 folder.</p>
<p>- There will be two folders inside. Scripts and Upload. </p>
<p>- Pause on this folder and move the window to the side for now. We'll be back for this in a couple seconds.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT31" src="https://github.com/user-attachments/assets/d1811c77-75f4-4f00-b2d8-b54b95a42732" />
    </td>
    <td>
      <img width="1000" alt="OT32" src="https://github.com/user-attachments/assets/6c8bb4ae-a65f-45ba-b711-5e0fd7e886b8" />
    </td>
  </tr>
</table>
<p>- Use File Explorer and navigate to the C drive. (Windows(C:).</p>
<p>- Open inetpub. Within inetpub, open wwwroot. </p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT33" src="https://github.com/user-attachments/assets/d4928144-2b92-4380-883a-68ca3e5edcc7" />
    </td>
    <td>
      <img width="1000" alt="OT34" src="https://github.com/user-attachments/assets/6d2ea203-60ba-4fb5-9082-1734c954934e" />
    </td>
  </tr>
</table>
<p>- Now, drag the "upload" folder from "osTicket-v1.15.8" folder and drop into the "wwwroot" folder.</p>
<p>- DO NOT just copy and paste. I made this mistake during my first run through of the lab and osTicket failed to launch at the end.🤦‍♂️😩  </p>
<p>- Confirm the "upload" folder actually moved from "osTicket-v1.15.8" and into "wwwroot". See Figure 33</p>
<br/>

<img width="600" alt="OT35" src="https://github.com/user-attachments/assets/e44f2551-3c10-47ce-88de-7efc70d636ee" />

<p>- Within "wwwroot", rename "upload" to "osTicket" exactly like in Figure 34. </p>
<p>- This is another area where people stuggled during the lab. So double check before moving on. </p>
<p>- Next, we'll need to reload IIS again. (Stop, Start the web server) From the Start Menu, run IIS as an Admin. Right-click osTicket-vm and click Stop. Wait a couple seconds, then right-click osTicket-vm and click Start. Refer back to Figure 26 and Figure 27 if needed.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" height="350" alt="OT38" src="https://github.com/user-attachments/assets/27d503c2-ef04-4100-b1bf-abf209c1c014" />
    </td>
    <td>
      <img width="1000" alt="OT39" src="https://github.com/user-attachments/assets/e6f78834-d85d-4958-b823-2adfcc5065db" />
    </td>
  </tr>
</table>
<p>- Since we're already in IIS. Lets check our work and attempt to load the osTicket site..</p>
<p>- In IIS on the left side of the screen, under Connections, go in this order:</p> 
 <p> osTicket-vm -> Sites -> Default Web Site -> osticket. (See Figure 35) /p>
<p>- Then on the left side, under Browse Folder, click Browse *:80 (http).</p>
<p>- Well looky there! We did it! Trust me when I say this is a GREAT sign. This means that we've done evrything correct up to this point.🎉 </p>
<p>- Alright, settle down because there's still work to be done. We need to grab some missing extensions before we can party. See Figure 36</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT40" src="https://github.com/user-attachments/assets/a304e8c4-1876-4289-ae04-041c6dd65b68" />
    </td>
    <td>
      <img width="1000" alt="OT41" src="https://github.com/user-attachments/assets/ab2161b6-9cc7-47bc-80da-303396c58671" />
    </td>
  </tr>
</table>
<p>- In IIS, go Sites -> Default Web Site -> osTicket. Double-click PHP. </p>
<p>- Under PHP Extensions, click "Enable or disable an extension". This opens PHP Extensions and will allow us to enable the ones we're missing.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT42" src="https://github.com/user-attachments/assets/577fd5f4-171d-4e7b-8a3b-a2fb330f171b" />
    </td>
    <td>
      <img width="1000" alt="OT43" src="https://github.com/user-attachments/assets/8419caa7-9ee7-410f-a61b-d6bf51f24ccf" />
    </td>
  </tr>
</table>
<p>- Scroll through and locate "php_imap.dll". Select and Enable. </p>
<p>- Scroll some more and locate "php_intl.dll". Select and Enable.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT44" src="https://github.com/user-attachments/assets/abe343fb-2dd3-41c3-8bc0-462075b4b331" />
    </td>
    <td>
      <img width="1000" alt="OT45" src="https://github.com/user-attachments/assets/9ec4be3e-bafc-4381-8618-64774db13552" />
    </td>
  </tr>
</table>
<p>- Last but not least, scroll through and locate "php_opcache.dll". Select and Enable. </p>
<p>- Now, you can simply refresh the browser and observe the new draft picks to the extension team. Fly Eagles Fly! 🦅 🏆 </p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT46" src="https://github.com/user-attachments/assets/ae88f162-18eb-4de5-af66-ad7101d4135c" />
    </td>
    <td>
      <img width="1000" alt="OT47" src="https://github.com/user-attachments/assets/a6049c4b-24dc-43a3-bc37-84fcfaea8459" />
    </td>
  </tr>
</table>
<p>- Next, we need to rename a config file and assign some permissions. </p>
<p>- Use File Explore and navigate this path: Windows(C:) -> inepub -> wwwroot -> osTicket. Open "include".</p>
<p>- Within "include", locate the "ost-sampleconfig.php" file. This is the file we need to rename.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT48" src="https://github.com/user-attachments/assets/3d07decb-060a-448b-b3a4-716ba195266d" />
    </td>
    <td>
      <img width="1000" alt="OT49" src="https://github.com/user-attachments/assets/e64a4ec1-5a1c-44aa-bf11-2d00a0f87578" />
    </td>
  </tr>
</table>
<p>- Rename "ost-sampleconfig.php" to "ost-config.php". Name it exactly like you see in Figure 45. This is another IMPORTANT step in our success later and everybody wants the Pizza Party! Andolini's Pizzeria is straight 🔥 if you're ever in Oklahoma! 😁  </p>
<p>- Now that we got the config file renamed correctly, right-click "ost-config.php" and click Properties.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="500" Height="450" alt="OT50" src="https://github.com/user-attachments/assets/3f262cb8-94f9-437c-979a-42c72cd40b7e" />
    </td>
    <td>
      <img width="1000" alt="OT51" src="https://github.com/user-attachments/assets/0dcccb1c-0c7c-4c5e-b285-52036c9386db" />
    </td>
  </tr>
</table>
<p>- We need to assign permissions for osTicket to make changes to this file on the backend.</p>
<p>- In Properties, select the Security tab and click Advanced. </p>
<p>- Click Disable inheritance.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT52" src="https://github.com/user-attachments/assets/cd2bb0a3-b748-4c38-b8ab-248647364007" />
    </td>
    <td>
      <img width="1000" alt="OT53" src="https://github.com/user-attachments/assets/c4b5c83b-22f1-4495-a123-2e0bcd849f89" />
    </td>
  </tr>
</table>
<p>- Select "Remove all inherited permissons from this object". </p>
<p>- Since all the permissions are gone now, click Add.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT54" src="https://github.com/user-attachments/assets/fb69374c-e4a8-4034-b94b-2dcd99b26c92" />
    </td>
    <td>
      <img width="1000" alt="OT55" src="https://github.com/user-attachments/assets/0ce68638-e626-4b4d-81e8-4ecaeb5a2460" />
    </td>
  </tr>
</table>
<p>- Click "Select a principal" and then in the box, type "everyone". This would not a good idea in the real world but its okay for this project. </p>
<p>- Hit "Check Names" and click OK.</p>
<p>- Next, check "Full control" and click OK.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT56" src="https://github.com/user-attachments/assets/e7b45e2e-cc2e-486d-99fa-2cf439909769" />
    </td>
    <td>
      <img width="500" height="450" alt="OT57" src="https://github.com/user-attachments/assets/d48c7a76-2e32-4853-9c73-bcb2285438fa" />
    </td>
  </tr>
</table>
<p>- Review the permission changes we made, confirm your screen looks like Figure 53, hit Apply, and click OK.</p>
<p>- We can see our changes here as well. Click OK.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT58" src="https://github.com/user-attachments/assets/cd36a756-1ca5-4e09-b40f-4053312ec347" />
    </td>
    <td>
      <img width="1000" alt="OT59" src="https://github.com/user-attachments/assets/a45d41a6-c605-45a5-8941-ad0afe07ff53" />
    </td>
  </tr>
</table>
<p>- Go back to the osTicket webpage in the browser and click Continue at the bottom of the page. We will finish setting up osTicket here.</p>
<p>- This is your Help Desk to name how you see fit. So do you boo.</p>
<p>- The Default email doesn't have to be a real email. Once you got this filled out, scroll down.</p>
<p>- Put yourself as the Admin User. This email doesn'matter either but it does need to be different from the one above.</p>
<p>- Username: "adminuser" Password: "Password1". Keep it simple and note this information for later. </p>
<p>- Before we fill out the Database Settings, we will need to install one last thing to get this information. </p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT60" src="https://github.com/user-attachments/assets/6dc3d06e-30e3-4fa3-956a-dc332b6cac2d" />
    </td>
    <td>
      <img width="1000" alt="OT61" src="https://github.com/user-attachments/assets/6bebe1fa-9e59-4314-a9f4-6ccf7b8c4eed" />
    </td>
  </tr>
</table>
<p>- We'll make one final visit to the "osTicket-Installation-Files" on our Desktop and install HeidiSQL.</p>
<p>- HeidiSQL is an application that allows us to make a connection to our database, configure it, and use our Help Desk super powers for the greater good.</p>
<p>- Find the "osTicket-Installation-Files" folder that's buried under the hundreds on windows we've opened so far. 🤣</p>
<p>- Select and download "HeidiSQL_12.3.0.6589_Setup". Agree, click Next, and Install. Make sure "Launch HeidiSQL" is checked, click Finish and Skip.</p>
<p>- Create a new Session Manager. Click +New. Under Settings, User is root and password is ROOT (VERY IMPORTANT). Click Open.</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT62" src="https://github.com/user-attachments/assets/21120f81-f277-4db9-b013-80712b35c638" />
    </td>
    <td>
      <img width="1000" alt="OT63" src="https://github.com/user-attachments/assets/f57d4bfa-5ae8-4bda-9e1b-01e0e44c75c2" />
    </td>
  </tr>
</table>
<p>- Right-click the dolphin Unamed, select Create new, and click Database.</p>
<p>- Name the database "osTicket". This is another IMPORTANT step towards our success. Click OK. See Figure 60</p>
<br/>

<table>
  <tr>
    <td>
      <img width="1000" alt="OT64" src="https://github.com/user-attachments/assets/d43b69fc-9119-4b54-a4a3-e8cc672c671b" />
    </td>
    <td>
      <img width="1000" alt="OT65" src="https://github.com/user-attachments/assets/81757509-c7c7-438a-bc28-90ae592bb7ae" />
    </td>
  </tr>
</table>
<p>- Now back to the browser to complete the Database Settings</p>
<p>- MySQL Database: osTicket - MySQL Username: root - MySQL Password: ROOT</p>
<p>- Click Install Now.</p>
<p>- CONGRATULATIONS! We did it! osTicket has been successfully installed. </p>
<p>- Take note of the URLs on Figure 62. We'll break these down in the next project, but check out the Stall Control Panel. </p>
<br/>

<img width="600" alt="OT66" src="https://github.com/user-attachments/assets/8ab1af80-d866-45ee-9c74-979b0c408f0d" />

<p>- There's just something about riding off in the sunset. Lets take a moment to reflect upon the journey we just embarked.</p>
<br/>





