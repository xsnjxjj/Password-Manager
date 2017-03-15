# Password Manager  
[![Build Status](https://travis-ci.org/zeruniverse/Password-Manager.svg)](https://travis-ci.org/zeruniverse/Password-Manager)
[![Codacy Badge](https://api.codacy.com/project/badge/grade/b5d954be72144355aa258748cfd05bca)](https://www.codacy.com/app/zzy8200/Password-Manager)
![License](https://img.shields.io/github/license/zeruniverse/Password-Manager.svg)
![Environment](https://img.shields.io/badge/PHP-5.2+-blue.svg)
![Environment](https://img.shields.io/badge/MySQL-required-ff69b4.svg)     
**'master' branch is a dev-branch, please download stable version from [Release](https://github.com/zeruniverse/Password-Manager/releases) in order to use.**      
  
Benjamin has started the [PwChromeExtension](https://github.com/BenjaminHae/PwChromeExtension) project [[DOWNLOAD](https://github.com/BenjaminHae/PwChromeExtension/releases/latest)], which provides a Chrome and Firefox extension for Password-Manager.  
  
##Version  
v9.13   
Supports are available [here](https://github.com/zeruniverse/Password-Manager/issues) for versions greater than v9.0   
From v9.13, Password-Manager only supports **HTTPS** 
  
##DEMO   
[phppasswordmanager.sourceforge.io](https://phppasswordmanager.sourceforge.io)  
This demo is for test ONLY! Do NOT put your real password there.  
You can access the database for this demo [here](https://mysql-p.sourceforge.net), with login username **p2663268ro** and password **12345678**   
  
Additional test demo available here: [pas.jeffery.cc](http://pas.jeffery.cc/)  
This demo is for test purpose and might be unstable. Users are recommended to use the sourceforge demo.
    
##Features  
1. Client side encryption. Server only keeps the encrypted strings.  
2. Customized fields support. You can add/delete fields for the password manager. For example, you might want a URL field to keep login URL for all your accounts.  
3. PIN login. You don't need to input your long login password everytime. Instead, you can use a short PIN, in your trusted devices.   
4. Files support. You can attach files to accounts. Of course, files are encrypted in your browser before they are uploaded.  
5. Tags support and searching support. This makes it easier to manage lots of accounts.  
6. Import/Export as CSV file.   
7. Easy to use backup/recovery.  
8. Authentication control. Account/IP will be blocked for too many failed attempts. After a short time of no action, you'll sign out automatically.  
9. Friendly UI.  
    
##Installation  
See [wiki](https://github.com/zeruniverse/Password-Manager/wiki/Installation)   
  
##How to use
See [wiki](https://github.com/zeruniverse/Password-Manager/wiki)  

##Mechanism 
This password manager can generate and store random strong passwords for users. Passwords are generated on users' browsers and then encrypted using AES256 (mode CBC). Key for encryption is generated by PBKDF2 based on login password (Password_1)   
PBKDF2 with SHA512 is used for user identification check. Raw password will be mapped to a pseudo password with a key related to Password_1 before applying AES256. The mapping algorithm is alphabet and position based.    
Some part of information in Password_1 won't involve in calculations for identity check, So password_1 can't be obtained by enumerating password_0 (used for authentication).  
  
<img width="1098" alt="mechanism" src="https://cloud.githubusercontent.com/assets/4648756/13795540/b0dfde78-eabe-11e5-8407-e5904dad59d2.png">    
  
You can read more information about implementation in [wiki](https://github.com/zeruniverse/Password-Manager/wiki/Mechanism).  
  
##Extentions  
You can easily add E-mail verification, Google authentication... in your version of password manager. Put your implementation inside `check.php`, which is used for login authentication.   
  
##Copyright  
Jeffery Zhao (Full list in LICENSE file)   
License: MIT  
The copyrights for libraries (such as Crypto-JS and Bootstrap) are reserved by their authors.    
Cooperators with significant contributions will become co-owner of this copyright and noted in LICENSE.   
All contributors to this project must agree their work to be published under MIT license ONLY (see LICENSE file) before submitting a pull request.   
