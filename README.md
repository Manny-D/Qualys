# Qualys

![Qualys](https://github.com/Manny-D/Qualys/assets/99146530/3a0d6890-1c57-4fd9-956a-4168835f94d1) <br>

## Description

In this project, I will go through the process of installing a Qualys Virtual Scanner Appliance using VirtualBox, which will then be accessed through the Qualys Cloud Platform. Once configured, I will scan a Windows virtual machine, remediate the vulnerabilities and verify the VM is no longer vulnerable. 

<b>Note:</b> This is utilizing the Qualys Community Edition and assumes you have VirtualBox and an unpatched Windows virtual machine already installed.

<br>

### Download & Configure Qualys Virtual Scanner Appliance
From the main page, click on Download a virtual scanner listed next to number 2, <b>Configure a scanner appliances:</b> <br>
![Screenshot 2024-04-01 at 6 28 02 PM (3)](https://github.com/Manny-D/Qualys/assets/99146530/e1eb5662-b6da-4589-b94e-0f62e2013615) <br>

In the Add New Virtual Scanner pop-up that appears, under Get Started, click on Start Wizard: <br>
![Screenshot 2024-04-01 at 6 34 59 PM](https://github.com/Manny-D/Qualys/assets/99146530/5dddb944-7e9a-48c8-a821-e2ce848bd947) <br>

Name your scanner whatever you want it to be and click Next: <br>
![Screenshot 2024-04-01 at 7 48 12 PM](https://github.com/Manny-D/Qualys/assets/99146530/04f2d880-a2c7-4406-8fb9-6a3bd5b4a722) <br>

Under Choose a Virtualization Platform, select VMWare ESXi, vCenter Server (standard) (this applies to VirtualBox): <br>
![Screenshot 2024-04-01 at 8 04 00 PM](https://github.com/Manny-D/Qualys/assets/99146530/6ee8e948-d919-4856-971e-22076495d6f6) <br>
(see supported Virtualization Platforms [here](https://docs.qualys.com/en/scanner/supported-platform/get_started/supported_virtualization_platforms.htm).) <br>

Click Next so that it begins the download of your .ova file.

The Add New Virtual Scanner pop-up will still be visible, scroll down to the bottom and click Next. <br>

You will now be given you Personalization Code to be used once the Qualys Virtual Scanner Appliance is installed: <br>
![Screenshot 2024-04-01 at 8 31 30 PM](https://github.com/Manny-D/Qualys/assets/99146530/516ab9da-3de1-4a22-a780-85100e4c9657) <br>

<br>

Once .ova file is downloaded, within VirtualBox Manager, click on File -> Import Appliance <br>

You will see the following pop-up. Click on the folder icon (to the far right of File):
![Screenshot 2024-04-01 at 8 09 09 PM](https://github.com/Manny-D/Qualys/assets/99146530/92e605fc-8647-4a61-9017-172ee6a13f19) <br>

Select the .ova file that was downloaded -> Next -> Next -> Finish: <br>
![Screenshot 2024-04-01 at 8 11 52 PM](https://github.com/Manny-D/Qualys/assets/99146530/27392753-22ae-4dd9-aee8-a293a68aa290) <br>

<br>

Once the Qualys Virtual Scanner Appliance is installed in VirtualBox, double click on it and the Qualys Scanner Console will open: <br>
![Screenshot 2024-04-01 at 8 22 20 PM](https://github.com/Manny-D/Qualys/assets/99146530/b6d8b640-83ea-434e-baf4-a12b2c479a1e) <br>
Enter the personalization code you were provided in the pop-up, and it will connect to your Qualys Cloud Profile. <br>

<br>

When the Scanner Appliance is connected to your Cloud Profile, another popup will appear with the Virtual Scanner Name you provided and the IP address it was assigned within VirtualBox: <br>
![Screenshot 2024-04-01 at 8 47 46 PM](https://github.com/Manny-D/Qualys/assets/99146530/bad1a7cf-7e08-4b6f-a6b8-82af047c4261) <br>

Go back to the Add New Virtual Scanner pop-up, scroll to the bottom and click on Check Activation: <br>
![Screenshot 2024-04-01 at 8 49 10 PM](https://github.com/Manny-D/Qualys/assets/99146530/ccadfc92-7837-43d2-8b62-bef53dd6f359) <br>

Upon verification <br>
![Screenshot 2024-04-01 at 8 53 19 PM](https://github.com/Manny-D/Qualys/assets/99146530/98cba90a-8abe-4e23-add3-087a1ab34e05) <br>

the Scanner Appliance will appear under the Appliances tab in your Cloud Profile: <br>
![Screenshot 2024-04-01 at 8 52 34 PM](https://github.com/Manny-D/Qualys/assets/99146530/d6c02009-c184-4064-b8d9-760e1b65f1f1) <br>

<br>

Now we need to setup the scanning range that Qualys will be scanning. <br>

Click on Assets -> Add IP's for Scanning: <br>
![Screenshot 2024-04-01 at 8 57 15 PM](https://github.com/Manny-D/Qualys/assets/99146530/6a1681b8-6de2-4520-89b2-d2aa3b6f87e9) <br>

Click on New -> IP Tracked Addresses: <br>
![Screenshot 2024-04-01 at 8 58 40 PM](https://github.com/Manny-D/Qualys/assets/99146530/a4cf5c4e-d762-4856-8980-cb3c8b9cb7e5) <br>

In the Add Hosts pop-up, click Subscription IPs and add the IPs that your home router provides: <br>
![Screenshot 2024-04-01 at 9 01 22 PM](https://github.com/Manny-D/Qualys/assets/99146530/7de32e19-fd7f-459b-9b3f-dca9cdc84560) <br>

Once added, scroll to the bottom of the pop-up and click Add and the configuration should be completed: <br>
![Screenshot 2024-04-01 at 9 06 06 PM](https://github.com/Manny-D/Qualys/assets/99146530/89a4ff75-2a24-45d8-ab06-6b137b4b7a5e) <br>

<br>

### Setting up a Scan
In the Qualys Cloud, click on Scans -> Option Profiles -> New -> Option Profile: <br>
![Screenshot 2024-04-01 at 9 31 33 PM](https://github.com/Manny-D/Qualys/assets/99146530/daccdd75-da79-4313-9574-4d48a90751ff) <br>

In the New Option Profile pop-up, in the Option Profile Title section, enter a Title: <br>
![Screenshot 2024-04-01 at 9 32 42 PM](https://github.com/Manny-D/Qualys/assets/99146530/2c0a4016-51eb-496f-b198-6a74aba19874) <br>
As we'll be performing a non-authenticated scan first, click on Save.

The new Scan Profile should now appear: <br>
![Screenshot 2024-04-01 at 9 41 54 PM](https://github.com/Manny-D/Qualys/assets/99146530/57477bbb-9a9a-49a3-8458-6b05dbb410f1) <br>

<br>

### Running a Non-Authenticated Scan
Click on the Scans tab -> New -> Scan: <br>
![Screenshot 2024-04-01 at 9 43 34 PM](https://github.com/Manny-D/Qualys/assets/99146530/fcb296fb-4e14-44e0-b37e-a603e58c4718) <br>

In the Launch Vulnerability Scan pop-up: add a Title, select the Option Profile created earlier, select the Scanner Appliace created at the beginning and add the IP Addresses/Ranges of what you're scanning (not shown in the screenshot), then click Launch: <br>
![Screenshot 2024-04-01 at 9 48 40 PM](https://github.com/Manny-D/Qualys/assets/99146530/c14f5526-74a1-4549-956b-da9a610f3d52) <br>
<b>Note</b>: Unless specified, all the other options / settings can be left at their defaults. <br>

<br>

Qualys should now be running a non-authenticated scan: <br>
![Screenshot 2024-04-01 at 9 57 07 PM](https://github.com/Manny-D/Qualys/assets/99146530/d400a361-fbc0-4de6-b3bb-c97f1f7332af) <br>
If it fails, you may need to check if the Windows Firewall / Defender is enabled on your VM. If so, disable it and run the scan again. <br>

<br>

#### Non-Authenticated Scan Results
The scan yielded negligable results: <br>
![Screenshot 2024-04-01 at 10 00 01 PM](https://github.com/Manny-D/Qualys/assets/99146530/63ca8466-cfa0-4ebd-ac36-d7e29d1faf08) <br>

So we will run an Authenticated Scan next!

<br>

### Authenticated Scan - Initial Setup
<b>Important note</b>: <br>
In order for the authenticated scan to work properly, I will need to update specific settings in the Admin profile being used within the Windows VM. Under normal circumstances, the Qualys scanning profile would already have this pre-configured. <br>

<b>Services</b>: <br>
For both Remote Registry and Server <br>
Startup type: Automatic <br>
Manually Start (if not already running) <br>

<b>Advanced sharing settings</b>: <br>
Confirm Network Discovery and File and printer sharing are both on. <br> 

<b>User Account Control (UAC) Settings</b>: <br>
Set to Never notify <br>

<b>Windows Registry</b>: <br>
Create a new entry under: <br> 
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System -> right click -> New -> DWORD (32-bit) Value <br>
Value name: LocalAccountTokenFilterPolicy <br>
Value data: 1 <br>

<br>

### Running an Authenticated Scan
Click on Scans -> Authentication -> New -> Operating Systems -> Windows <br>
![Screenshot 2024-04-01 at 10 27 15 PM](https://github.com/Manny-D/Qualys/assets/99146530/30a854fe-72ed-435d-a317-191857f8dd28) <br>

In the New Windows Record pop-up, enter a title: <br>
![Screenshot 2024-04-01 at 10 28 41 PM](https://github.com/Manny-D/Qualys/assets/99146530/a15528a4-1036-4692-ac72-39d53c402de6) <br>

Click on the Login Credentals section -> Windows Authentication, tick Local -> under Login, enter in the Windows VM Admin credentials: <br>
![Screenshot 2024-04-01 at 10 32 16 PM](https://github.com/Manny-D/Qualys/assets/99146530/99fa913e-3967-4326-9a6b-387ea60774e2) <br>

Click on IPs -> add the IP of the Windows VM -> Save: <br>
![Screenshot 2024-04-01 at 10 34 42 PM](https://github.com/Manny-D/Qualys/assets/99146530/5787928b-0bad-4156-b93d-877ffd0fc815) <br>

<br>

Click on Option Profiles -> tick the Basic Net Scan -> move to the right and click on the yellow down arrow -> Edit: <br>
![Screenshot 2024-04-01 at 10 42 08 PM](https://github.com/Manny-D/Qualys/assets/99146530/db598625-2b2b-43ea-925c-1d1773922d6a) <br>

In the Edit Option Profile pop-up, click on Scan -> scroll down to Authentication -> tick Windows -> scroll down -> Save: <br>
![Screenshot 2024-04-01 at 10 44 09 PM](https://github.com/Manny-D/Qualys/assets/99146530/4a136474-a774-4330-a057-f23ffe9a9282) <br>

<br>

Let's create a new scan title to differentiate between the non-authenticated and authenticated scans!

Click on the Scans tab -> New -> Scan <br>
![Screenshot 2024-04-01 at 10 46 52 PM](https://github.com/Manny-D/Qualys/assets/99146530/ab210388-db24-436d-a911-ffda7f68a75f) <br>

Enter a new title, select the Option Profile created earlier, select the Scanner Appliace created at the beginning and add the IP Addresses/Ranges of what you're scanning, then click Launch: <br>
![Screenshot 2024-04-01 at 10 50 13 PM](https://github.com/Manny-D/Qualys/assets/99146530/b819e873-c325-4eb2-87cc-75f7850a63f1) <br>
<b>Note</b>: The screenshot does not show all the correctly selected fields. <br>

<br>

Qualys should now be running an authenticated scan: <br>
![Screenshot 2024-04-01 at 9 57 07 PM](https://github.com/Manny-D/Qualys/assets/99146530/d400a361-fbc0-4de6-b3bb-c97f1f7332af) <br>

<br>

#### Authenticated Scan Results <br>
117 Vulnerabilities! <br>
![Screenshot 2024-04-01 at 10 59 57 PM](https://github.com/Manny-D/Qualys/assets/99146530/d016a8bb-4374-456b-b482-21c4b29037ab) <br>

<br>

### Remediating Vulnerabilities and Re-scanning to Verify Results <br>
Ran Windows Update and downloaded updates / patches for various software on the VM. <br>
Performed another authenticated scan. <br> 
Vulnerabilities were reduced to 27. <br>
![Screenshot 2024-04-01 at 11 08 01 PM](https://github.com/Manny-D/Qualys/assets/99146530/3cf3f6c0-fb94-484e-92ac-8dc7f2a4dca7) <br>
