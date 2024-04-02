# Qualys

![Qualys](https://github.com/Manny-D/Qualys/assets/99146530/3a0d6890-1c57-4fd9-956a-4168835f94d1) <br>

## Description

In this project, I will go through the process of installing a Qualys Virtual Scanner Appliance using VirtualBox, which will be access through the Qualys Cloud Platform. Once configured, I will scan a Windows virtual machine, remediate the vulnerabilities and verify the VM is no longer vulnerable. 

<b>Note:</b> This is utilizing the Qualys Community Edition and assumes you already have an unpatched Windows virtual machine installed.

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

When the Scanner Appliance is connected to your Cloud Profile, another popup will appear with the Virtual Scanner Name you provided and the IP address it was assigned within VirtualBox: <br>
![Screenshot 2024-04-01 at 8 47 46 PM](https://github.com/Manny-D/Qualys/assets/99146530/bad1a7cf-7e08-4b6f-a6b8-82af047c4261) <br>

Go back to the Add New Virtual Scanner pop-up, scroll to the bottom and click on Check Activation: <br>
![Screenshot 2024-04-01 at 8 49 10 PM](https://github.com/Manny-D/Qualys/assets/99146530/ccadfc92-7837-43d2-8b62-bef53dd6f359) <br>

Upon verification <br>
![Screenshot 2024-04-01 at 8 53 19 PM](https://github.com/Manny-D/Qualys/assets/99146530/98cba90a-8abe-4e23-add3-087a1ab34e05) <br>

the Scanner Appliance will appear under the Appliances tab in your Cloud Profile: <br>
![Screenshot 2024-04-01 at 8 52 34 PM](https://github.com/Manny-D/Qualys/assets/99146530/d6c02009-c184-4064-b8d9-760e1b65f1f1) <br>


Now we need to setup the scanning range that Qualys will be scanning. <br>

Click on Assets -> Add IP's for Scanning: <br>
![Screenshot 2024-04-01 at 8 57 15 PM](https://github.com/Manny-D/Qualys/assets/99146530/6a1681b8-6de2-4520-89b2-d2aa3b6f87e9) <br>

Click on New -> IP Tracked Addresses: <br>
![Screenshot 2024-04-01 at 8 58 40 PM](https://github.com/Manny-D/Qualys/assets/99146530/a4cf5c4e-d762-4856-8980-cb3c8b9cb7e5) <br>

In the Add Hosts pop-up, click Subscription IPs and add the IPs that your home router provides: <br>
![Screenshot 2024-04-01 at 9 01 22 PM](https://github.com/Manny-D/Qualys/assets/99146530/7de32e19-fd7f-459b-9b3f-dca9cdc84560) <br>

Once added, scroll to the bottom of the pop-up and click Add and the configuration should be completed: <br>
![Screenshot 2024-04-01 at 9 06 06 PM](https://github.com/Manny-D/Qualys/assets/99146530/89a4ff75-2a24-45d8-ab06-6b137b4b7a5e) <br>

