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

1
<p>
<p>
<img <img width="1440" alt="ACN_101" src="https://github.com/user-attachments/assets/cad3752c-9778-42ca-8284-0136b0771a62" />
</p>
<p>
2
<p>
<img <img width="1440" alt="ACN_102" src="https://github.com/user-attachments/assets/4ea9d8bf-75df-4ecc-a8bf-dba3e67caf7f" />
</p>
<p>
3
<p>
<img <img width="1440" alt="ACN_103" src="https://github.com/user-attachments/assets/5c3576df-80e9-4e40-b723-7869f508958b" />
</p>
<p>
4
<p>
<img <img width="1440" alt="ACN_104" src="https://github.com/user-attachments/assets/f5cad6a3-1b90-4d53-9c4b-39e43b442fbd" />
</p>
<p>
5
<p>
<img <img width="1440" alt="ACN_105" src="https://github.com/user-attachments/assets/8c51d03b-d21c-4e96-b6be-18b70f9612f2" />
</p>
<p>
6
<p>
<img <img width="1440" alt="ACN_106" src="https://github.com/user-attachments/assets/5be16917-fb9b-4036-8224-bedf6f126b71" />
</p>
<p>
7
<p>
<img <img width="1440" alt="ACN_107" src="https://github.com/user-attachments/assets/c43dbfed-2f81-4b29-b0df-38a5f081330a" />
</p>
<p>
8
<p>
<img <img width="1440" alt="ACN_108" src="https://github.com/user-attachments/assets/3dddbb33-64f7-479a-9000-657ef4344f93" />
</p>
<p>
9
<p>
<img <img width="1440" alt="ACN_109" src="https://github.com/user-attachments/assets/6d2d7ac0-c625-4b4b-954c-40565779d41f" />
</p>
<p>
10
<p>
<img <img width="1440" alt="ACN_110" src="https://github.com/user-attachments/assets/3e456a0e-c70d-4a04-8d82-a9087b100ec4" />
</p>
<p>
11
<p>
<img <img width="1440" alt="ACN_111" src="https://github.com/user-attachments/assets/b34dfe40-2453-4b98-a7ca-0e92b80bac2f" />
</p>
<p>
12
<p>
<img <img width="1440" alt="ACN_112" src="https://github.com/user-attachments/assets/4c90ea8b-42ef-4e01-8eb6-5e5b3b44dc68" />
</p>
<p>
13
<p>
<img <img width="1440" alt="ACN_113" src="https://github.com/user-attachments/assets/4f746567-060a-4896-9098-fd97a1728631" />
</p>
<p>
14
<p>
<img <img width="1440" alt="ACN_114" src="https://github.com/user-attachments/assets/16055d77-9b0b-4463-8f17-2a9196085940" />
</p>
<p>
15
<p>
<img <img width="1440" alt="ACN_115" src="https://github.com/user-attachments/assets/02046a62-0fe1-410c-b82f-4ef409e2cd2a" />
</p>
<p>
16
<p>
<img <img width="1440" alt="ACN_116" src="https://github.com/user-attachments/assets/aa70ca03-3fb2-4430-b05d-6cc9ffb018c6" />
</p>
<p>
17
<p>
<img <img width="1440" alt="ACN_117" src="https://github.com/user-attachments/assets/7fef13f2-33c9-46b7-80f6-7b60028332a9" />
</p>
<p>
18
<p>
<img <img width="1440" alt="ACN_118" src="https://github.com/user-attachments/assets/cf31e2f8-09c7-41c4-8212-839690c0d9a0" />
</p>
<p>
19
<p>
<img <img width="1440" alt="ACN_119" src="https://github.com/user-attachments/assets/c661969c-3e99-476a-b460-811d6186fb0a" />
</p>
<p>
20
<p>
<img <img width="1440" alt="ACN_120" src="https://github.com/user-attachments/assets/d20fe1ea-5208-4a8b-a2b9-02c1081de85b" />
</p>
<p>
21
<p>
<img <img width="1440" alt="ACN_121" src="https://github.com/user-attachments/assets/6031ca4a-c2f4-4f4c-b0f3-876c22d3f95f" />
</p>
<p>
22
<p>
<img <img width="1440" alt="ACN_122" src="https://github.com/user-attachments/assets/8297f780-ba38-4259-82f4-bbae91950bd7" />
</p>
<p>
23
<p>
<img <img width="1440" alt="ACN_123" src="https://github.com/user-attachments/assets/90f26527-7099-4969-96ea-39f367fd14df" />
</p>
<p>
24
<p>
<img <img width="1440" alt="ACN_124" src="https://github.com/user-attachments/assets/346334d3-5fd0-457e-b9ba-a4d282f3ac3c" />
</p>
<p>
25
<p>
<img <img width="1440" alt="ACN_125" src="https://github.com/user-attachments/assets/026b9464-ddd1-4cc0-84a7-3ad645b4d864" />
</p>
<p>
26
<p>
<img <img width="1440" alt="ACN_126" src="https://github.com/user-attachments/assets/0acafdb6-a554-4cc3-b9b5-486722697303" />
</p>
<p>
27
<p>
<img <img width="1440" alt="ACN_127" src="https://github.com/user-attachments/assets/19be2a71-6ab7-419e-b611-dbac83a41e73" />
</p>
<p>
28
<p>
<img <img width="1440" alt="ACN_128" src="https://github.com/user-attachments/assets/b3bc9db9-5b8c-47f9-a3c4-ab017d5d1933" />
</p>
<p>
29
<p>
<img <img width="1440" alt="ACN_129" src="https://github.com/user-attachments/assets/c98e0771-4405-4a34-b302-815d8a426de7" />
</p>
<p>
30
<p>
<img <img width="1440" alt="ACN_130" src="https://github.com/user-attachments/assets/089c8843-0236-4b17-9f2f-2cf12172eb66" />
</p>
<p>
31
<p>
<img <img width="1440" alt="ACN_131" src="https://github.com/user-attachments/assets/6c2719ae-8848-4c5e-82f1-4a64ccb8597d" />
</p>
<p>
32
<p>
<img <img width="1440" alt="ACN_132" src="https://github.com/user-attachments/assets/7b9fbbe3-b71d-4409-8a0c-5e7bcaa96bbc" />
</p>
<p>
33
<p>
<img <img width="1440" alt="ACN_133" src="https://github.com/user-attachments/assets/6814b672-a72f-48f4-9fab-220c87029628" />
</p>
<p>
34
<p>
<img <img width="1440" alt="ACN_134" src="https://github.com/user-attachments/assets/1f98131a-3e22-42c4-9a68-0674fe764d63" />
</p>
<p>
35
<p>
<img <img width="1440" alt="ACN_135" src="https://github.com/user-attachments/assets/55d1ea11-a9f2-41f9-a587-6f195eaeb613" />
</p>
<p>
36
<p>
<img <img width="1440" alt="ACN_136" src="https://github.com/user-attachments/assets/f32ba077-b447-45b5-9ff2-d21e225ebf9a" />
</p>
<p>
37
<p>
<img <img width="1440" alt="ACN_137" src="https://github.com/user-attachments/assets/95c04c75-0558-4e5c-a3a0-f796442eb15e" />
</p>
<p>
38
<p>
<img <img width="1440" alt="ACN_138" src="https://github.com/user-attachments/assets/61801b9c-aaa8-4307-803d-cba3f8fe1edb" />
</p>
<p>
39
<p>
<img <img width="1440" alt="ACN_139" src="https://github.com/user-attachments/assets/9ae66e10-8421-40e5-bf5a-a0a99492136d" />
</p>
<p>
40
<p>
<img <img width="1440" alt="ACN_140" src="https://github.com/user-attachments/assets/143ab3c9-1cda-4178-976d-eacf4ebe174a" />
</p>
<p>
41
<p>
<img <img width="1440" alt="ACN_141" src="https://github.com/user-attachments/assets/9c3de0d5-df01-496e-a34b-4ad793e5705b" />
</p>
<p>
42
<p>
<img <img width="1440" alt="ACN_142" src="https://github.com/user-attachments/assets/c989af3d-46e3-4818-a9e5-d45e6bca7741" />
</p>
<p>
43
<p>
<img <img width="1440" alt="ACN_143" src="https://github.com/user-attachments/assets/0725eab7-e494-4f98-a97b-1c1aefa2e667" />
</p>
<p>
44
<p>
<img <img width="1440" alt="ACN_144" src="https://github.com/user-attachments/assets/63138b81-60aa-409a-93c5-a853a4f7a1bb" />
</p>
<p>
45
<p>
<img <img width="1440" alt="ACN_145" src="https://github.com/user-attachments/assets/960f435d-6520-47be-bb7f-33f0bfd80579" />
</p>
<p>
46
<p>
<img <img width="1440" alt="ACN_146" src="https://github.com/user-attachments/assets/264554f5-0f51-47a0-86c2-4c64bc883a4f" />
</p>
<p>
47
<p>
<img <img width="1440" alt="ACN_147" src="https://github.com/user-attachments/assets/671a0045-ac2b-4aa2-acf6-112da09731ba" />
</p>
<p>
48
<p>
<img <img width="1440" alt="ACN_148" src="https://github.com/user-attachments/assets/cbb6f972-173d-4680-9bd0-7eb7b33d6128" />
</p>
<p>
49
<p>
<img <img width="1440" alt="ACN_149" src="https://github.com/user-attachments/assets/67261ac0-cabe-40f2-bc21-7ae51fe2e9b0" />
</p>
<p>
50
<p>
<img <img width="1440" alt="ACN_150" src="https://github.com/user-attachments/assets/61188719-1e65-4714-8777-90fcc0bc8586" />
</p>
<p>
51
<p>
<img <img width="1440" alt="ACN_151" src="https://github.com/user-attachments/assets/f963d514-12f9-440a-a6c4-7a7bbd3884e5" />
</p>
<p>
52
<p>
<img <img width="1440" alt="ACN_152" src="https://github.com/user-attachments/assets/80d3f500-01ca-4f59-bfa5-d6c6ceaf3246" />
</p>
<p>
53
<p>
<img <img width="1440" alt="ACN_153" src="https://github.com/user-attachments/assets/93e32906-f93d-4e2c-b0f0-8e6c9db20943" />
</p>
<p>
54
<p>
<img <img width="1440" alt="ACN_154" src="https://github.com/user-attachments/assets/38a157ed-8f84-4d4c-965e-8db5c275cb72" />
</p>
<p>
55
<p>
<img <img width="1440" alt="ACN_155" src="https://github.com/user-attachments/assets/6a118f92-38c2-4f04-8ae4-05659d6f390d" />
</p>
<p>
56
<p>
<img <img width="1440" alt="ACN_156" src="https://github.com/user-attachments/assets/dc085477-4380-41b5-b8dc-3052df27330e" />
</p>
<p>
57
<p>
<img <img width="1440" alt="ACN_157" src="https://github.com/user-attachments/assets/98ae4976-1485-4ffa-8a98-a258b9b5a5e1" />
</p>
<p>
58
<p>
<img <img width="1440" alt="ACN_158" src="https://github.com/user-attachments/assets/d9187105-ea6d-4b78-9215-667687aa78ee" />
</p>
<p>
59
<p>
<img <img width="1440" alt="ACN_159" src="https://github.com/user-attachments/assets/b330c6f3-ba54-4bfb-b9b7-7f73955d7102" />
</p>
<p>
60
<p>
<img <img width="1440" alt="ACN_160" src="https://github.com/user-attachments/assets/e108f79a-2ce1-462e-8525-83fe9ddacd5a" />
</p>
<p>
61
<p>
<img <img width="1440" alt="ACN_161" src="https://github.com/user-attachments/assets/25f9f9bc-cfb3-49a9-8b19-73f07c049d69" />
</p>
<p>
62
<p>
<img <img width="1440" alt="ACN_162" src="https://github.com/user-attachments/assets/57c39ccf-7539-4281-8675-bef2ed7c8151" />
</p>
<p>
63
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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
75
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
76
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
77
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
78
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
79
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
80
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
81
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
82
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
83
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
84
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
85
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
86
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
87
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
88
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
89
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
90
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
91
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
92
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
93
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
94
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
95
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
96
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
97
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
98
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
99
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
100
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
101
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
102
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
103
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
104
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
105
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
106
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
107
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
108
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
109
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
110
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
111
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
112
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
113
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
114
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
115
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
116
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
117
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
118
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
119
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
120
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
121
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
122
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
123
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
124
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
125
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
126
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
127
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
