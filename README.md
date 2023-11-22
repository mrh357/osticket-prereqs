<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>High level steps</h2>

- ### [Download prerequisites and dependencies](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
- Create a VM in Azure
- Enable IIS
- Enable IIS management Console
- Enable World Wide Web Services
- Enable CGI
- Enabke Common HTTP features
- Use PHP manager to edit the webserver
- Install dependencies from the list
- Create a mySQL database
- Install osTicket on the server
- Link mySQL with heidi SQL
- Create help desk
- Create admin account
<br/>
<br/>

<h2>Creating a VM in Azure</h2>

<p>

</p>
<br />
1. go to https://portal.azure.com/#home and create an account if necessary <br/>
<br/>
2. Click "Virtual machines"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/6cd5c419-70f4-4157-ac6e-57105c9f25f1/screenshot.jpeg?tl_px=577,0&br_px=1437,480&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,203)


3\. Click "Create"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/2744cd7b-3dd8-4c5d-b911-becddb2563af/screenshot.jpeg?tl_px=0,0&br_px=859,480&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=47,195)


4\. Click "Virtual Machine"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/ec569a94-5b31-4ee5-b7d6-1151bcfb343b/screenshot.jpeg?tl_px=0,28&br_px=859,509&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=56,212)


5\. Create a resource group, if necessary

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/92eca998-d9ed-4a0c-978e-0b7e3be5c714/screenshot.jpeg?tl_px=0,338&br_px=859,819&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=272,212)


6\. Name your resourse group

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/50b1d061-91d5-4e3d-a598-9afbff20e77c/screenshot.jpeg?tl_px=0,98&br_px=1719,1059&force_format=png&width=1120.0)


7\. Click "OK"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/f91e94fd-8d3c-40be-8e64-6088707d9065/screenshot.jpeg?tl_px=0,507&br_px=859,988&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=306,212)


8\. Click "Virtual machine name"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/949cd7b5-d627-4baf-ac70-0f2341c3bddb/screenshot.jpeg?tl_px=0,406&br_px=859,887&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=322,212)


9\. Name your VM

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/13e223c4-3e6f-42e9-8a84-5da1aa43c242/screenshot.jpeg?tl_px=0,166&br_px=1719,1127&force_format=png&width=1120.0)


10\. Click "Availability options"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/0caef4dd-13d2-46ef-9212-88f5b1df8f7d/screenshot.jpeg?tl_px=0,479&br_px=859,960&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=374,212)


11\. Click no redundancy (ONLY FOR THIS LAB. keep the redundancy if you need it for your operation)

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/1014dc78-9389-41cf-8cf7-5c7961f8579a/screenshot.jpeg?tl_px=0,515&br_px=859,996&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=359,212)


12\. Click "Image"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/3e1c31da-f471-47f1-9842-a4f74ac5803f/screenshot.jpeg?tl_px=41,376&br_px=900,857&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


13\. This lab used Windows 10

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/8cc4e8c5-2ffa-47ee-bcae-509236e012cc/screenshot.jpeg?tl_px=34,806&br_px=893,1287&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


14\. Click "size" and Create a VM with 2-4 CPU cores

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/28f09567-8557-481e-b104-dc7c2f8c1cf0/screenshot.jpeg?tl_px=62,389&br_px=921,870&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


15\. Create username"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/42365ec4-dd0c-43d1-b1d3-34ca693a5847/screenshot.jpeg?tl_px=0,242&br_px=1719,1203&force_format=png&width=1120.0)


16\. Create password

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/4ea319c9-a403-49b7-b7fb-a92d52e4e14b/screenshot.jpeg?tl_px=0,242&br_px=1719,1203&force_format=png&width=1120.0)


17\. Confirm password

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/ee36562f-b39e-420e-bb75-d0ac10cda4a9/screenshot.jpeg?tl_px=0,242&br_px=1719,1203&force_format=png&width=1120.0)


18\. Click "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights."

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/fbc46dcb-5714-4f24-8c97-43a5ba952721/screenshot.jpeg?tl_px=0,959&br_px=859,1440&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=27,272)

<br />
<br />
18.5. If you have specific networking, disk or other requirements, click continue and configure them through the wizard
<br />
<br />

19. Click "Review + create"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/470ac859-d18c-4d7f-9ea2-5a13c98716e6/screenshot.jpeg?tl_px=0,959&br_px=859,1440&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=99,371)


20\. Click "Create" and wait for it to tell you  "Deployment Successful"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/9e7d4100-df23-47a5-af4a-e3b6b1c8a7f0/screenshot.jpeg?tl_px=0,959&br_px=859,1440&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=31,372)
<br />
<br />
<h2>Accessing the VM</h2>

21\. Click on the Resource Group

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/c8abbc17-0be3-42ad-b2b4-d643b6548330/screenshot.jpeg?tl_px=376,243&br_px=1236,724&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


22\. Click on the VM

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/fa4544c0-6706-4dee-b7b6-b252b1ed8626/screenshot.jpeg?tl_px=0,337&br_px=859,818&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=353,212)


23\. Copy the Public IP address

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/5529ab44-ce88-47c3-a50f-fd359e28f2b2/screenshot.jpeg?tl_px=1220,127&br_px=2080,608&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


24\. Type "rdp"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/e505645c-75fb-477b-bcf7-da53acf76495/screenshot.jpeg?tl_px=0,478&br_px=1719,1440&force_format=png&width=1120.0)


25\. Click "Remote Desktop Connection"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/a43df2ae-415c-42c8-b7d8-484456fa1d30/screenshot.jpeg?tl_px=0,651&br_px=859,1132&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=206,212)


26\. Paste in or type in the public IP address

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/5bd9c019-4e6c-4505-966b-72eda3b7d192/screenshot.jpeg?tl_px=826,253&br_px=1686,734&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


27\. Enter the username and password you made when you were creating the VM

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/e6b53424-6616-4af6-acb4-b38d1ffc644d/screenshot.jpeg?tl_px=481,37&br_px=2201,998&force_format=png&width=1120.0)

28\. Click "Yes"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/0faf018a-54d4-4fc8-8c68-a7dd97a6f23d/screenshot.jpeg?tl_px=925,347&br_px=1785,828&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

<h2>Enabling IIS</h2>

29\. Open control panel

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/645eced8-2152-4b85-a191-521f73096c46/screenshot.jpeg?tl_px=690,168&br_px=1550,649&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


30\. Go to programs

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/fd835a0b-21f5-42ee-9d25-065309f99842/screenshot.jpeg?tl_px=478,431&br_px=1338,912&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


31\. Go to programs and features

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/f9ef2018-b978-498b-aae8-99054f814d88/screenshot.jpeg?tl_px=514,186&br_px=1374,667&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


32\. Click Turn Windows features on or off

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/68fca3c8-e07b-495f-b885-fed0cd2af3aa/screenshot.jpeg?tl_px=280,234&br_px=1140,715&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

33\. Enable Internet Information Services (IIS)

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/ece000eb-0c94-4f72-a4fa-464b60981767/screenshot.jpeg?tl_px=370,378&br_px=1230,859&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


34\. Expand IIS

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/829f66b9-0368-46c9-8d6a-786a0c5ad833/screenshot.jpeg?tl_px=377,377&br_px=1237,858&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


35\. Expand Web Management Tools

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/1f73109b-f3f9-46f4-bedd-2e91147db05d/screenshot.jpeg?tl_px=386,418&br_px=1246,899&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


36\. Enable IIS Management Console

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/7f8db91b-1265-472a-b9ba-466bdcc34e37/screenshot.jpeg?tl_px=385,380&br_px=1245,861&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


37\. Expand World Wide Web Services

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/213f38fd-0210-45ce-93c7-e69fe2f51c31/screenshot.jpeg?tl_px=388,399&br_px=1248,880&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


38\. Expand Application Development Features

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/91f60b6b-a995-409f-8f91-3ac93d1bbffd/screenshot.jpeg?tl_px=406,325&br_px=1266,806&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

39\. Enable CGI

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/788bdea0-3bfb-46fc-a07e-42835dbb5ff9/screenshot.jpeg?tl_px=403,322&br_px=1263,803&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

40. Enable Common HTTP Features
![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/b99eca1f-7a31-47c6-9b31-41ea4ef42179/screenshot.jpeg?tl_px=405,376&br_px=1265,857&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)



41\. Click ok

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/95c43839-3427-4ab3-aec5-c145e128a383/screenshot.jpeg?tl_px=611,493&br_px=1471,974&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


42\. Click close

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/afec4262-8c67-4283-956c-8b732228fa10/screenshot.jpeg?tl_px=859,545&br_px=1719,1026&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)



43\. To make sure IIS is working, go to a browser and type "127.0.0.1". If it shows a blue page and does not return an error it worked!

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/d35a95d6-50a1-43cb-b0dc-1793a0479a2c/screenshot.jpeg?tl_px=0,0&br_px=1719,961&force_format=png&width=1120.0)

<h2>Installing prerequisites</h2>

44\. Open File Explorer

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/a4a5b7a8-f03c-4a22-aa57-f62913efbc74/screenshot.jpeg?tl_px=72,959&br_px=931,1440&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,434)


45\. Type "c:\" in the address bar and hit enter

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/942d449a-3190-4a4f-b4f2-b4e75b3019c9/screenshot.jpeg?tl_px=164,0&br_px=1883,961&force_format=png&width=1120.0)


46\. Create a new folder named "PHP"
![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/1e614b12-8886-4a9b-8920-1826c065808d/screenshot.jpeg?tl_px=393,437&br_px=2113,1398&force_format=png&width=1120.0)

47. In a new tab, open the [Prerequisite Files Download Folder](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
<br />
<br/>
48. Download and install PHPManagerForIIS_V1.5.0.msi <br />
<br/>
49. Download and install rewrite_amd64_en-US.msi<br />
<br/>
50. Download the zip file php-7.3.8-nts-Win32-VC15-x86.zip. Then extract this folder to C:\PHP<br /> 
<br/>
51 Download and install VC_redist.x86.exe. <br/>
<br />
52. Download and install 'mysql-5.5.62-win32.msi' and do the Typical Setup

53\. Click launch mysql after install

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/a692ed22-120d-4438-83f2-11adf670dd70/screenshot.jpeg?tl_px=847,582&br_px=1707,1063&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


54\. Standard configuration (unless you need a detailed configuration)

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/5af9e8f4-0af6-4d0b-91d6-8a0a7b4bd57c/screenshot.jpeg?tl_px=244,410&br_px=1104,891&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


55\. MySQL and click next

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/0c2aabce-3dcd-44dc-be9e-5f0370460383/screenshot.jpeg?tl_px=211,404&br_px=1071,885&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


56\. Create a root password for MYSQL click next,

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/1c876986-c346-4e55-8b83-ec2256823333/screenshot.jpeg?tl_px=147,194&br_px=1006,675&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


57\. Click execute then click finish when done 

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/ec4ca012-06ba-48db-8588-6fc118710d58/screenshot.jpeg?tl_px=236,408&br_px=1096,889&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


58\. Search for IIS and run as administrator

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/b1c1286f-d5c6-4de3-a7b8-3d864749710d/screenshot.jpeg?tl_px=0,667&br_px=859,1148&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=273,212)


59\. Click PHP manager

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/3caae09a-52ba-44bb-bac0-d58463557f41/screenshot.jpeg?tl_px=991,99&br_px=1851,580&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


60\. Register new PHP

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/63beb19b-b96a-4ab2-aea5-870bc1181056/screenshot.jpeg?tl_px=30,225&br_px=890,706&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


61\. Go to 'C:\PHP' and add the PHP-cgi application to the registration and click OK
![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/7644b76d-be2f-484f-9572-82ed340303f0/screenshot.jpeg?tl_px=614,545&br_px=1474,1026&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


62\. Go back to the main screen and click restart on the right side under manage server

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/52a82063-0a8c-4901-b5dc-2c03798e3025/screenshot.jpeg?tl_px=1523,80&br_px=2383,561&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


63\. Download 'osTicket v1.15.8' and extract the folder to 'c:\inetpub\wwwroot'<br/>
<br/>
64. Go to the osTicket folder and rename 'upload' folder to 'osTicket'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/140ca46f-b211-4f16-8c07-34f18c281608/screenshot.jpeg?tl_px=0,268&br_px=859,749&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=382,212)


65\. Go back to the IIS manager and restart the server

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/ea9869b2-22df-44fc-8172-e1b735a8b75c/screenshot.jpeg?tl_px=1518,96&br_px=2378,577&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


66\. On the left side, click to expand sites

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/25ea4c36-86ed-47cc-ac97-351a96a92c0b/screenshot.jpeg?tl_px=0,92&br_px=859,573&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=212,212)


67\. Expand default sites and click on osTicket

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/158c9e2e-80f3-466f-b767-a44fb63b4ed7/screenshot.jpeg?tl_px=0,127&br_px=859,608&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=250,212)

68\. On the right side, click on 'browse *:80 (http)'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/4baaec79-1e53-4391-b420-412cbd95836f/screenshot.jpeg?tl_px=1561,128&br_px=2421,609&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


69\. On this page, you will see some extensions we need to activate. (keep the window open)

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/479fc9a8-d73c-4ecb-b309-95cf0fd557d5/screenshot.jpeg?tl_px=455,328&br_px=1315,809&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


70\. Go back to the IIS manager-> PHP manager-> enable PHP extensions

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/9e7d0478-1656-4f3b-8cce-64439eaf07cb/screenshot.jpeg?tl_px=165,528&br_px=1025,1009&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


71\. right click and enable 'php_imap.dll'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/be3521e4-21e7-4b8b-aea5-659a2784a3b1/screenshot.jpeg?tl_px=123,542&br_px=982,1023&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


72\. Right click and enable 'php_intl.dll'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/353e1607-677d-4c9f-a3a1-8977efb5a18a/screenshot.jpeg?tl_px=95,565&br_px=955,1046&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


73\. Right click and enable php_opcache.dll

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/c20ecfd9-b299-428f-948b-1fc656f65b00/screenshot.jpeg?tl_px=90,660&br_px=949,1141&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

74\. Go back to the main menu of IIS manager and restart the server

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/fa2734d7-dbb8-47f4-b059-5beca0c161f4/screenshot.jpeg?tl_px=1524,90&br_px=2384,571&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

75\. Refrecsh the browser window with osTicket and everything is enabled.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/653741af-7dec-4ad7-83b7-64e8d3d521aa/screenshot.jpeg?tl_px=465,313&br_px=1325,794&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

76\. Go into 'C:\inetpub\wwwroot\osticket\include'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/976ddd2d-4adc-40f3-940d-26e38d27cef2/screenshot.jpeg?tl_px=0,342&br_px=859,823&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=389,212)


77\. Rename 'ost-sampleconfig.php' ->'ost-config.php'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/6a98c983-84f3-45da-96d8-d3f2e3dffb7e/screenshot.jpeg?tl_px=28,618&br_px=887,1099&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


78\. Right click on 'ost-config.php' and choose properties

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/9f26d3a5-13ea-451c-b512-c01b4a2852e9/screenshot.jpeg?tl_px=143,887&br_px=1002,1368&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

79\. Click security and advanced

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/c84d855e-89ff-4352-a5a4-a86b60fdf173/screenshot.jpeg?tl_px=257,539&br_px=1117,1020&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


80\. Click "disable inheritance'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/e73fb039-293f-42d6-bce8-cf8fea49ff7c/screenshot.jpeg?tl_px=540,646&br_px=1400,1127&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

81\. Click add and select a principal
![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/0dbf3778-d087-4258-b5c8-bb8681a0dd06/screenshot.jpeg?tl_px=529,220&br_px=1389,701&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

82\. Type 'everyone' click check name,

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/560d1388-7fe3-4369-9adc-acf1c9249089/screenshot.jpeg?tl_px=738,418&br_px=1598,899&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


83\. Give full control and click ok on both windows

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/1850b13e-8340-4135-a759-5c0af0a8c7ec/screenshot.jpeg?tl_px=491,346&br_px=1351,827&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


84\. Click 'continue' in the osTicket browser windows

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/dc1df8d8-7a6d-4865-b0d4-230b68f739ed/screenshot.jpeg?tl_px=707,555&br_px=1567,1036&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)

<h2>osTicket install</h2>

85\. Create your primary admin account

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/80b786cc-ef32-4db9-893b-43d523d7fa92/screenshot.jpeg?tl_px=536,394&br_px=1396,875&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


86\. Go back to the install files and download the heidisql12.3.0.6589setup.exe

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/db6276ba-957f-411c-859b-37d279932182/screenshot.jpeg?tl_px=716,256&br_px=1576,737&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


87\. Agree to terms and continue through, and make sure it launches heidisql after install and click finsh

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/cdf330d4-ad72-4672-863b-b621783a6570/screenshot.jpeg?tl_px=999,665&br_px=1859,1146&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


88\. Click new 

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/3e27389d-1bd4-4d90-9dc1-94e691ad6f82/screenshot.jpeg?tl_px=0,507&br_px=859,988&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=294,212)


89\. Enter the username and password from when you set up MYSQL earlier and click open

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/a25baca0-aea9-4247-9915-710aff47044e/screenshot.jpeg?tl_px=317,289&br_px=1177,770&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


90\. Right click on the list of databases on the left and click create new database

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/502ee46a-1a08-4c8d-a042-e041934b8cf3/screenshot.jpeg?tl_px=280,184&br_px=1140,665&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


91\. Name it "osTicket"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/fa06132b-1b4d-4c19-b5ad-c30e24371399/screenshot.jpeg?tl_px=0,0&br_px=1719,961&force_format=png&width=1120.0)


92\. Click ok

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/4578f4c0-4794-424d-9e84-40ff451464d7/screenshot.jpeg?tl_px=416,253&br_px=1276,734&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


93\. back in the osTicket web gui, enter osTicket for the name

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/4dcabece-5b82-45ef-bf92-7b5ba0858e8e/screenshot.jpeg?tl_px=539,847&br_px=1399,1328&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


94\. Click "Input Capture Window"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/5c4ee70f-9436-401c-ad62-600ae5bd0bbe/screenshot.jpeg?tl_px=513,904&br_px=1373,1385&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


95\. Enter you database's username and password

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/1d3e4f64-a231-47b3-95ec-1889c01c01f9/screenshot.jpeg?tl_px=502,952&br_px=1362,1433&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,212)


96\. If everything went well, you should see this screen and osTicket is installed!

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-11-02/990627da-962f-4083-8cb0-cdd350b07fcc/screenshot.jpeg?tl_px=359,0&br_px=1219,480&force_format=png&width=860&wat_scale=76&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=402,-19)




