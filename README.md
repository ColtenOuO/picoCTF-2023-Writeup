# picoCTF-2023-Writeup

## Overview

We have participated in picoCTF 2023 competition, which is organised by Carnegie Mellon University and ran from Mar 15 2023 to Mar 29 2023.

The following is our write up of the challenges we solved during the contest.

## Team

### NCKU-LeafLeafLeaf (National Cheng Kung University)

![image](https://user-images.githubusercontent.com/70793703/229209720-b9e226d7-0ec7-43f7-9dec-6a812bcf3c6f.png)

# General Skills

## chrono 

Use ssh to connect to the server.

in path `/` has a directory named `challenge`.

Use **cd** command to `challenge` and **ls** to check what is inside the directory.

![](https://i.imgur.com/utvV0Wh.png)

Use **cat** command to open the JSON file, and we can get the flag.

![](https://i.imgur.com/ILuWoIM.png)

## money-ware

We can search **1Mz7153HMuxXTuR2R1t78mGSdzaAtNbBWX** in browser.

![](https://i.imgur.com/3zV87qY.png)

As we can see, the flag is **picoCTF{Petya}**

## Permissions

Use ssh to connect to the server.

in path `/` has a directory named `challenge`.

Use **cd** command to `challenge` and **ls** to check what is inside the directory.

![](https://i.imgur.com/rQiyUTO.png)

Open the JSON file by **vim** and get the flag.

![](https://i.imgur.com/2lEiIEl.png)

# Crypto
## ReadMyCert
```
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF83ODM0
YzVmMn0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBALNCq27+10dci/gQ/bBxzqtEOgogaab6zG529aIuKsI9w1mzUgNl
Gd70Vjc6SNTGRAEWbQasM8zCN9iX6wgmmotE+m4/1/7+QkxuFxvfdJOCygNd0rtI
sJdtzC7ZeG3XJF3ny+FOGrP1xni7xWIpIjwfXtEcprO65WReVIFlaHEGSx/qRMBW
gI00BRcGWEuk1XgRMXof63Z71l0tyAiNcVuivSTOf6OHH1FNbdO3wKXy094QCIt8
yxn5OAKi3EAiASaT6hYKjcs6elCV3YTi4uxJMw3mCZQ6G8yhRhdv92H1A5xQwtQT
WTpPF7CA0eJyrmctFIETpBvWTNWfP5rorBUCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAGhIGd79
u4lUC3hC0ipPPdVfAZph9Wjbjnu9dofixMjheH+v4+NU8xXOlVw0sVB6+xyB6iOA
K+uQ6w/F0n4tlcF2AkHX4yY81gN4dpQdPD9KPQwLd/ay2Ya2a5p/+/SVyZto2YCn
QDG48eJy0tyZaAl8XxGRpADsyXXGGBaxCF2GJ4y9tAHe8qeqRochSKzQCkWACwZW
0p/mxQERsT8TOdkVjyTRSkcp3tP6MdrreotXUjNWFe71jZtDoGMcs1CYOCbUmTl3
x8/g2tumZI7FHeCybZHdsjm7Xawwf66LgaEodH4KT8mWtZzUcrKDhwn54EmnevMh
UFreOOreZZh9ZE8=
-----END CERTIFICATE REQUEST-----
```
CSR decoder :D
https://www.sslshopper.com/csr-decoder.html

# Reverse

## timer
apk file decompile
http://www.javadecompilers.com/processing


# Web
## more SQLi
```
username: admin
password: qwertyuiop
SQL query: SELECT id FROM users WHERE password = 'qwertyuiop' AND username = 'admin'
```
login payload : 
password = `'OR 1==1 --`
登入以後出現的畫面(the page after login):`welcome.php`
<img src="https://i.imgur.com/9QIzhse.png" width=300></img>
input payload : `' UNION SELECT id,name,password FROM users --`
and gets
<img src="https://i.imgur.com/t0JGx0p.png" width=300></img>
id : 1
name: admin
password: moreRandOMN3ss

