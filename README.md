<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

1 Opening up the Internet Protocol you can see the source becomes the Linux VM and the destination is the Windows VM. 
  This will be the process for all the pings afrer. 
<p>
<p>
<img <img width="1440" alt="ACN_101" src="https://github.com/user-attachments/assets/cad3752c-9778-42ca-8284-0136b0771a62" />
</p>
<p>
2 Next we are going to configure a fire wall. 
  First step in the Windows Vm we are going to do a perpetual ping in powershell. 
  Like before ping the private IP address of the linux computer with a -t at the end and it enter. 
<p>
<img <img width="1440" alt="ACN_102" src="https://github.com/user-attachments/assets/4ea9d8bf-75df-4ecc-a8bf-dba3e67caf7f" />
</p>
<p>
3 As you will begin to see this ping will be nonstop. 
<p>
<img <img width="1440" alt="ACN_103" src="https://github.com/user-attachments/assets/5c3576df-80e9-4e40-b723-7869f508958b" />
</p>
<p>
4 You will also be able to see this being captured in Wireshark as well. 
<p>
<img <img width="1440" alt="ACN_104" src="https://github.com/user-attachments/assets/f5cad6a3-1b90-4d53-9c4b-39e43b442fbd" />
</p>
<p>
5 For another example click the green shark fin again and "Continue without Saving". 
<p>
<img <img width="1440" alt="ACN_105" src="https://github.com/user-attachments/assets/8c51d03b-d21c-4e96-b6be-18b70f9612f2" />
</p>
<p>
6 The pings will continue to request and reply. 
<p>
<img <img width="1440" alt="ACN_106" src="https://github.com/user-attachments/assets/5be16917-fb9b-4036-8224-bedf6f126b71" />
</p>
<p>
7 Now we are going to go back into azure and configure the firewall to disable incoming ICMP traffic. 
  Go to Virtual machines and click the "Linux-vm".
<p>
<img <img width="1440" alt="ACN_107" src="https://github.com/user-attachments/assets/c43dbfed-2f81-4b29-b0df-38a5f081330a" />
</p>
<p>
9 Click the drop down arroe for Networking and then click "Network settings". 
<p>
<img <img width="1440" alt="ACN_109" src="https://github.com/user-attachments/assets/6d2d7ac0-c625-4b4b-954c-40565779d41f" />
</p>
<p>
10 Scroll down and click "Linux-vm-nsg" under Network security group. (aka the firewall)
<p>
<img <img width="1440" alt="ACN_110" src="https://github.com/user-attachments/assets/3e456a0e-c70d-4a04-8d82-a9087b100ec4" />
</p>
<p>
12 Here go to settings on the left and click "Inbaound security rules". 
<p>
<img <img width="1440" alt="ACN_112" src="https://github.com/user-attachments/assets/4c90ea8b-42ef-4e01-8eb6-5e5b3b44dc68" />
</p>
<p>
13 Now we are going to create a rule for traffic comming inbound to the virtual machine. 
   Click "Add".  
<p>
<img <img width="1440" alt="ACN_113" src="https://github.com/user-attachments/assets/4f746567-060a-4896-9098-fd97a1728631" />
</p>
<p>
15 Source: Any 
   Destination: Any 
   Service: Custom 
   Destination port ranges: Use an * (ICMP doesn't have a port).
   Protocol: ICMPv4
   Action: Deny
   Priority: 290 (This will make so this rule is evaluated first.)
   Now click "Add" 
<p>
<img <img width="1440" alt="ACN_115" src="https://github.com/user-attachments/assets/02046a62-0fe1-410c-b82f-4ef409e2cd2a" />
</p>
<p>
16 Now your rule has been added to the Inbound security rules. 
<p>
<img <img width="1440" alt="ACN_116" src="https://github.com/user-attachments/assets/aa70ca03-3fb2-4430-b05d-6cc9ffb018c6" />
</p>
<p>
17 Back in the Windows VM the pings will keep coming until the rule takes affect. 
   Once it does you will see "Request timed out" in Powershell for any incoming ICMP traffic. 
<p>
<img <img width="1440" alt="ACN_117" src="https://github.com/user-attachments/assets/7fef13f2-33c9-46b7-80f6-7b60028332a9" />
</p>
<p>
19 If you go back to Wireshark instead of seeign request and reply you will only see request and no response found. 
<p>
<img <img width="1440" alt="ACN_119" src="https://github.com/user-attachments/assets/c661969c-3e99-476a-b460-811d6186fb0a" />
</p>
<p>
20 Now we are going to re-enable ICMP traffic in the network settings. 
   Go back int azure go to virtal machines > Linux-vm > Network settings > Linux-vm-nsg and click Inbound Security rules. 
<p>
<img <img width="1440" alt="ACN_120" src="https://github.com/user-attachments/assets/d20fe1ea-5208-4a8b-a2b9-02c1081de85b" />
</p>
<p>
21 From here we are going to Delete this rule 
   Click the trash can on the right for the rule we created. 
<p>
<img <img width="1440" alt="ACN_121" src="https://github.com/user-attachments/assets/6031ca4a-c2f4-4f4c-b0f3-876c22d3f95f" />
</p>
<p>
22 Click "Yes". 
<p>
<img <img width="1440" alt="ACN_122" src="https://github.com/user-attachments/assets/8297f780-ba38-4259-82f4-bbae91950bd7" />
</p>
<p>
23 With that rule deleted go back to the Windows VM. 
<p>
<img <img width="1440" alt="ACN_123" src="https://github.com/user-attachments/assets/90f26527-7099-4969-96ea-39f367fd14df" />
</p>
<p>
25 In Wireshark you will notice the incoming traffic has gpone back to request and reply between the two VM's. 
<p>
<img <img width="1440" alt="ACN_125" src="https://github.com/user-attachments/assets/026b9464-ddd1-4cc0-84a7-3ad645b4d864" />
</p>
<p>
26 The same for Powershell will go from timed out back to continued replies. 
<p>
<img <img width="1440" alt="ACN_126" src="https://github.com/user-attachments/assets/0acafdb6-a554-4cc3-b9b5-486722697303" />
</p>
<p>
27 Now we can stop this ping activity in powershell by clicking Control c will and it will stop. 
<p>
<img <img width="1440" alt="ACN_127" src="https://github.com/user-attachments/assets/19be2a71-6ab7-419e-b611-dbac83a41e73" />
</p>
<p>
28 Next stop the Wirshark as well by click the red box in the top left to "Stop capturing packets". 
<p>
<img <img width="1440" alt="ACN_128" src="https://github.com/user-attachments/assets/b3bc9db9-5b8c-47f9-a3c4-ab017d5d1933" />
</p>
<p>
29 In the Windows VM we are going to observer SSH (Secure Shell Protocol). 
<p>
<img <img width="1440" alt="ACN_129" src="https://github.com/user-attachments/assets/c98e0771-4405-4a34-b302-815d8a426de7" />
</p>
<p>
32 First, open up wireshark if it isnt and click "Ethernet" then click the blue shark fin to start a new packet captrue and you will see the spam.  
<p>
<img <img width="1440" alt="ACN_132" src="https://github.com/user-attachments/assets/7b9fbbe3-b71d-4409-8a0c-5e7bcaa96bbc" />
</p>
<p>
33 We need the private IP address for the Linux VM. Go back the the Virtial machines in Azure and click "Linux-vm".
<p>
<img <img width="1440" alt="ACN_133" src="https://github.com/user-attachments/assets/6814b672-a72f-48f4-9fab-220c87029628" />
</p>
<p>
34 In Overview scroll down to the private IP address and copy it. 
<p>
<img <img width="1440" alt="ACN_134" src="https://github.com/user-attachments/assets/1f98131a-3e22-42c4-9a68-0674fe764d63" />
</p>
<p>
35 Open up Powershell. 
<p>
<img <img width="1440" alt="ACN_135" src="https://github.com/user-attachments/assets/55d1ea11-a9f2-41f9-a587-6f195eaeb613" />
</p>
<p>
37 Go back to Wireshark filter for SSH traffic. 
<p>
<img <img width="1440" alt="ACN_137" src="https://github.com/user-attachments/assets/95c04c75-0558-4e5c-a3a0-f796442eb15e" />
</p>
<p>
38 Back in Powershell type "ssh labuser@<private IP address> and press enter. 
<p>
<img <img width="1440" alt="ACN_138" src="https://github.com/user-attachments/assets/61801b9c-aaa8-4307-803d-cba3f8fe1edb" />
</p>
<p>
39 This will generate ssh traffic. 
   In Powershell you will also be asked "Are you syre you want to continue connecting."
<p>
<img <img width="1440" alt="ACN_139" src="https://github.com/user-attachments/assets/9ae66e10-8421-40e5-bf5a-a0a99492136d" />
</p>
<p>
40 Type yes and press enter. 
<p>
<img <img width="1440" alt="ACN_140" src="https://github.com/user-attachments/assets/143ab3c9-1cda-4178-976d-eacf4ebe174a" />
</p>
<p> 
41 Now type in the password for the Linux vm user and press enter 
   (You wont be able to see it because it is encrypted but the txt is there.)
<p>
<img <img width="1440" alt="ACN_141" src="https://github.com/user-attachments/assets/9c3de0d5-df01-496e-a34b-4ad793e5705b" />
</p>
<p>
42 Then you will see something like labuser@linux-vm. Now you are actually connected inside the Linux machine. 
<p>
<img <img width="1440" alt="ACN_142" src="https://github.com/user-attachments/assets/c989af3d-46e3-4818-a9e5-d45e6bca7741" />
</p>
<p>
43 As an example type "id" and press enter. 
<p>
<img <img width="1440" alt="ACN_143" src="https://github.com/user-attachments/assets/0725eab7-e494-4f98-a97b-1c1aefa2e667" />
</p>
<p>
44 This will show the linux user id. 
<p>
<img <img width="1440" alt="ACN_144" src="https://github.com/user-attachments/assets/63138b81-60aa-409a-93c5-a853a4f7a1bb" />
</p>
<p>
45 IF we type "hostname" and press enter
<p>
<img <img width="1440" alt="ACN_145" src="https://github.com/user-attachments/assets/960f435d-6520-47be-bb7f-33f0bfd80579" />
</p>
<p>
46 The hostname you made for the linux machine will pop up. 
<p>
<img <img width="1440" alt="ACN_146" src="https://github.com/user-attachments/assets/264554f5-0f51-47a0-86c2-4c64bc883a4f" />
</p>
<p>
47 If you want to try this type "uname -a" and press enter. 
<p>
<img <img width="1440" alt="ACN_147" src="https://github.com/user-attachments/assets/671a0045-ac2b-4aa2-acf6-112da09731ba" />
</p>
<p>
48 THis will show information about the operating system on the Linux Machine.
<p>
<img <img width="1440" alt="ACN_148" src="https://github.com/user-attachments/assets/cbb6f972-173d-4680-9bd0-7eb7b33d6128" />
</p>
<p>
49 Meanwhile Wirshark has been capturing everything.
<p>
<img <img width="1440" alt="ACN_149" src="https://github.com/user-attachments/assets/67261ac0-cabe-40f2-bc21-7ae51fe2e9b0" />
</p>
<p>
50 Even single keystrokes. If you type anything you will see the traffic on the backend. 
<p>
<img <img width="1440" alt="ACN_150" src="https://github.com/user-attachments/assets/61188719-1e65-4714-8777-90fcc0bc8586" />
</p>
<p>
52 Now just because everything is captured that doesn't mean you can see it.
   All of SSH traffic is encrypted. 
   For example type "hi" (or something similar) aand press ent. 
   Then click on the packet created from it. 
<p>
<img <img width="1440" alt="ACN_152" src="https://github.com/user-attachments/assets/80d3f500-01ca-4f59-bfa5-d6c6ceaf3246" />
</p>
<p>
54 Now click "SSH Protocol", "SSH Version 2", and "Encrypted Packet". 
   In the box to the right that is the information from you typing but because of the encryption it wont show exactly what that was. 
<p>
<img <img width="1440" alt="ACN_154" src="https://github.com/user-attachments/assets/38a157ed-8f84-4d4c-965e-8db5c275cb72" />
</p>
<p>
58 Now just as another example in Powershell type "pwd" (Print Working Directory) and press enter. 
<p>
<img <img width="1440" alt="ACN_158" src="https://github.com/user-attachments/assets/d9187105-ea6d-4b78-9215-667687aa78ee" />
</p>
<p>
59 That command shows that the current shell is home/labuser.
<p>
<img <img width="1440" alt="ACN_159" src="https://github.com/user-attachments/assets/b330c6f3-ba54-4bfb-b9b7-7f73955d7102" />
</p>
<p>
60 You can also try the command "touch file.txt" an press enter. This will create a file on the linux machine. 
<p>
<img <img width="1440" alt="ACN_160" src="https://github.com/user-attachments/assets/e108f79a-2ce1-462e-8525-83fe9ddacd5a" />
</p>
<p>
62 If you type "ls" and press enter it will show you the file.txt was created. 
<p>
<img <img width="1440" alt="ACN_162" src="https://github.com/user-attachments/assets/57c39ccf-7539-4281-8675-bef2ed7c8151" />
</p>
<p>
63 As you are doing this you will be able to see all the SSH traffic being captured. 
<p>
<img <img width="1440" alt="ACN_163" src="https://github.com/user-attachments/assets/14f52435-afc0-4622-8e61-f0b30313f371" />
</p>
<p>
64 
<p>
<img <img width="1440" alt="ACN_164" src="https://github.com/user-attachments/assets/35edf31e-f940-4895-935e-90557c35db85" />
</p>
<p>
65
<p>
<img <img width="1440" alt="ACN_165" src="https://github.com/user-attachments/assets/40012e66-3ff8-42a7-9ac8-b149a0d4a9b3" />
</p>
<p>
66
<p>
<img <img width="1440" alt="ACN_166" src="https://github.com/user-attachments/assets/f6750cbe-58f4-4472-860f-748d99f36a1a" />
</p>
<p>
67
<p>
<img <img width="1440" alt="ACN_167" src="https://github.com/user-attachments/assets/78f3ae4a-9e27-434a-90ca-63a4de223ea6" />
</p>
<p>
68
<p>
<img <img width="1440" alt="ACN_168" src="https://github.com/user-attachments/assets/fd8cade8-8a7b-4c78-abd7-9abbed124795" />
</p>
<p>
69
<p>
<img <img width="1440" alt="ACN_169" src="https://github.com/user-attachments/assets/0126eb75-0e29-40d6-9c66-c0323a382f02" />
</p>
<p>
70
<p>
<img <img width="1440" alt="ACN_170" src="https://github.com/user-attachments/assets/037679a2-85a7-4d30-8a7a-b80f97253839" />
</p>
<p>
71
<p>
<img <img width="1440" alt="ACN_171" src="https://github.com/user-attachments/assets/9ac13088-1b54-4a41-bc2d-2d9dc0725db0" />
</p>
<p>
72
<p>
<img <img width="1440" alt="ACN_172" src="https://github.com/user-attachments/assets/4cf8db8d-477d-4ff8-bf6b-86b156c32f7c" />
</p>
<p>
73
<p>
<img <img width="1440" alt="ACN_173" src="https://github.com/user-attachments/assets/d366005f-0749-4474-8d04-0e9cbc3485ce" />
</p>
<p>
74
<p>
<img <img width="1440" alt="ACN_174" src="https://github.com/user-attachments/assets/6bf2133f-6e43-4df7-a2cc-6ccdb1b28d41" />
</p>
<p>
75
<p>
<img <img width="1440" alt="ACN_175" src="https://github.com/user-attachments/assets/ba06d142-6d03-43a0-9d21-5349e3a41714" />
</p>
<p>
76
<p>
<img <img width="1440" alt="ACN_176" src="https://github.com/user-attachments/assets/f56a43b4-f51f-4288-87af-2a6455deab48" />
</p>
<p>
77
<p>
<img <img width="1440" alt="ACN_177" src="https://github.com/user-attachments/assets/1025250a-25f6-4ada-ae07-355e0d7b26fd" />
</p>
<p>
78
<p>
<img <img width="1440" alt="ACN_178" src="https://github.com/user-attachments/assets/b3d42419-273e-445b-9570-f765d7ad7ed5" />
</p>
<p>
79
<p>
<img <img width="1440" alt="ACN_179" src="https://github.com/user-attachments/assets/be6cc4c2-28f5-4c8b-a610-34fce4df1ff3" />
</p>
<p>
80
<p>
<img <img width="1440" alt="ACN_180" src="https://github.com/user-attachments/assets/073dc90a-07a0-45cf-b0a7-8a71db9b0883" />
</p>
<p>
81
<p>
<img <img width="1440" alt="ACN_181" src="https://github.com/user-attachments/assets/3850f32e-aa5b-495c-a2f4-0e0f3fe86d99" />
</p>
<p>
82
<p>
<img <img width="1440" alt="ACN_182" src="https://github.com/user-attachments/assets/8faf78aa-5ab2-4a89-9513-7d3a669985e7" />
</p>
<p>
83
<p>
<img <img width="1440" alt="ACN_183" src="https://github.com/user-attachments/assets/104ea3ba-39a8-4f28-b36f-8951a8552cf8" />
</p>
<p>
84
<p>
<img <img width="1440" alt="ACN_184" src="https://github.com/user-attachments/assets/297e3578-12fe-4217-96a5-60206c23d7b8" />
</p>
<p>
85
<p>
<img <img width="1440" alt="ACN_185" src="https://github.com/user-attachments/assets/00d63d3b-b1e2-43e8-a573-e29eb532f135" />
</p>
<p>
86
<p>
<img <img width="1440" alt="ACN_186" src="https://github.com/user-attachments/assets/8bd0dc46-e09e-456b-8499-ca8a1122a63d" />
</p>
<p>
87
<p>
<img <img width="1440" alt="ACN_187" src="https://github.com/user-attachments/assets/de0997f2-1068-4745-b1c9-1f9d46f628d4" />
</p>
<p>
88
<p>
<img <img width="1440" alt="ACN_188" src="https://github.com/user-attachments/assets/28ce06d2-e99b-403b-86ae-ac6039788631" />
</p>
<p>
89
<p>
<img <img width="1440" alt="ACN_189" src="https://github.com/user-attachments/assets/27fb8462-2d9f-4db9-bb6c-4ec977bb84f4" />
</p>
<p>
90
<p>
<img <img width="1440" alt="ACN_190" src="https://github.com/user-attachments/assets/61210461-2f5a-4efc-9c98-785e9e9e44aa" />
</p>
<p>
91
<p>
<img <img width="1440" alt="ACN_191" src="https://github.com/user-attachments/assets/d70dc7d7-6bdf-4487-b153-84c130fa7bf0" />
</p>
<p>
92
<p>
<img <img width="1440" alt="ACN_192" src="https://github.com/user-attachments/assets/9c2dd6ce-6c51-4ec9-b803-767d6e9f38a8" />
</p>
<p>
93
<p>
<img <img width="1440" alt="ACN_193" src="https://github.com/user-attachments/assets/ef600f6a-c058-4625-86c0-0602161ae31f" />
</p>
<p>
94
<p>
<img <img width="1440" alt="ACN_194" src="https://github.com/user-attachments/assets/ae20366f-1043-4d1e-846b-3926939f2740" />
</p>
<p>
95
<p>
<img <img width="1440" alt="ACN_195" src="https://github.com/user-attachments/assets/5eb12ef4-aaf1-41f6-b806-28eb8b55394d" />
</p>
<p>
96
<p>
<img <img width="1440" alt="ACN_196" src="https://github.com/user-attachments/assets/e1c18549-488e-41d6-b2e8-9c82b4a12a0e" />
</p>
<p>
97
<p>
<img <img width="1440" alt="ACN_197" src="https://github.com/user-attachments/assets/051c7820-94fa-4799-9272-bb91588ea013" />
</p>
<p>
98
<p>
<img <img width="1440" alt="ACN_198" src="https://github.com/user-attachments/assets/c4281edf-2012-40d1-b8aa-ea6f2eef5d63" />
</p>
<p>
99
<p>
<img <img width="1440" alt="ACN_199" src="https://github.com/user-attachments/assets/44bc1d76-69b8-4eb6-92fe-e21d5dcd2b47" />
</p>
<p>
100
<p>
<img <img width="1440" alt="ACN_200" src="https://github.com/user-attachments/assets/778c0104-f918-47c4-a08f-6e277385c21e" />
</p>
<p>
101
<p>
<img <img width="1440" alt="ACN_201" src="https://github.com/user-attachments/assets/a3bc915f-c118-43ab-bba4-79a5d9573029" />
</p>
<p>
102
<p>
<img <img width="1440" alt="ACN_202" src="https://github.com/user-attachments/assets/2ff2c51b-0c22-4b34-8ccf-5c1c2d4f3d74" />
</p>
<p>
103
<p>
<img <img width="1440" alt="ACN_203" src="https://github.com/user-attachments/assets/121e3df8-58b7-471c-a094-967aa7d670cc" />
</p>
<p>
104
<p>
<img <img width="1440" alt="ACN_204" src="https://github.com/user-attachments/assets/66ee6ab3-c550-4ed4-8dcc-72fc5d66762a" />
</p>
<p>
105
<p>
<img <img width="1440" alt="ACN_205" src="https://github.com/user-attachments/assets/8b053cb4-9783-4415-8fef-27c5f47041df" />
</p>
<p>
106
<p>
<img <img width="1440" alt="ACN_206" src="https://github.com/user-attachments/assets/7bced678-6f44-4efb-b7ce-830d72bfb288" />
</p>
<p>
107
<p>
<img <img width="1440" alt="ACN_207" src="https://github.com/user-attachments/assets/f291b2ff-8cf9-40a9-813f-17f524f023f6" />
</p>
<p>
108
<p>
<img <img width="1440" alt="ACN_208" src="https://github.com/user-attachments/assets/ee5954cc-619f-4672-87a7-199f79fca455" />
</p>
<p>
109
<p>
<img <img width="1440" alt="ACN_209" src="https://github.com/user-attachments/assets/3bbf53d6-bcef-417d-980a-15c574d86caf" />
</p>
<p>
110
<p>
<img <img width="1440" alt="ACN_210" src="https://github.com/user-attachments/assets/8e37da63-ed9a-4086-86da-bac58b6ff1a8" />
</p>
<p>
111
<p>
<img <img width="1440" alt="ACN_211" src="https://github.com/user-attachments/assets/18d693cc-dc08-474a-9eea-3846ab4a2896" />
</p>
<p>
112
<p>
<img <img width="1440" alt="ACN_212" src="https://github.com/user-attachments/assets/571c5a31-1c73-472d-a46f-958b7a5711f8" />
</p>
<p>
113
<p>
<img <img width="1440" alt="ACN_213" src="https://github.com/user-attachments/assets/6b9d1f2b-e0dc-4466-988a-b5e29adaac1d" />
</p>
<p>
114
<p>
<img <img width="1440" alt="ACN_214" src="https://github.com/user-attachments/assets/9e62ffe3-6f46-4ca3-a4c1-bae60e35d9cf" />
</p>
<p>
115
<p>
<img <img width="1440" alt="ACN_215" src="https://github.com/user-attachments/assets/6e4424e2-dfec-4e46-ab17-24f366253145" />
</p>
<p>
116
<p>
<img <img width="1440" alt="ACN_216" src="https://github.com/user-attachments/assets/a29a4020-5436-40b7-b56e-48edc8a36156" />
</p>
<p>
117
<p>
<img <img width="1440" alt="ACN_217" src="https://github.com/user-attachments/assets/c1bdb30a-d29e-4156-bde0-e71d3e8db891" />
</p>
<p>
118
<p>
<img <img width="1440" alt="ACN_218" src="https://github.com/user-attachments/assets/475d7679-2e9f-44a1-b1b2-ee832c396746" />
</p>
<p>
119
<p>
<img <img width="1440" alt="ACN_219" src="https://github.com/user-attachments/assets/0d8de591-3cf6-45d9-8232-6cbf9a7edc07" />
</p>
<p>
120
<p>
<img <img width="1440" alt="ACN_220" src="https://github.com/user-attachments/assets/f72e1ace-1835-4287-a931-62f5b10a0539" />
</p>
<p>
121
<p>
<img <img width="1440" alt="ACN_221" src="https://github.com/user-attachments/assets/2d616759-ad75-4540-82e3-7bd37040d86a" />
</p>
<p>
122
<p>
<img <img width="1440" alt="ACN_222" src="https://github.com/user-attachments/assets/884a8c22-30ba-4d82-a2eb-ec2ac1c728b0" />
</p>
<p>
