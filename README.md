# Project 7 - WordPress Pentesting

Time spent: **15** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting(XSS1)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [x] GIF Walkthrough: 
    - <img src='XSS.gif' title='XSS' width='' alt='' />
  - [x] Steps to recreate: 
    - Create a new post
    - put following code in content link: ```<a onmouseover= "alert('I got you!')" >click here</a>```  
    - click link to show message
  - [x] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/branches/4.2/src/wp-includes/class-wp-editor.php?rev=33361)

2. (Required) Vulnerability Name or ID: User Enumeration
  - [x] Summary: 
    - Vulnerability types: User Enumeration
    - Tested in version: 4.2
    - Fixed in version: N/A
  - [x] GIF Walkthrough: 
    - <img src='UserEnumeration.gif' title='User Enumeration' width='' alt='' />
  - [x] Steps to recreate: 
    - Go to login page
    - input admin as username 
    - don't fill out password field
    - shows the password field is empty error
    - input admin as username 
    - input random password
    - shows the password you entered for the username admin is incorrect error  
    - input random username 
    - input random password
    - shows invalid username error
  - [x] Affected source code:
    - [Link 2](https://www.wpwhitesecurity.com/wordpress-security/wordpress-username-disclosure-vulnerability/)

3. (Required) Vulnerability Name or ID: Unauthenticated Stored Cross-Site Scripting (XSS2)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [x] GIF Walkthrough: 
    - <img src='XSS2.gif' title='XSS2' width='' alt='' />
  - [x] Steps to recreate: 
    - View new post
    - insert code ```<abbr title='Web......cedric' onmouseover='alert(1)' style='position:fixed;top:0;left:0;width:100%;height:100%'>``` in the comment under the post     - shows 1 when you view the comment after
  - [x] Affected source code:
    - [Link 3](https://cedricvb.be/post/wordpress-stored-xss-vulnerability-4-1-2/)

4. (Optional) Vulnerability Name or ID: Oversized File Upload Error Cross-Site Scripting (XSS3)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: 
    - <img src='XSS3.gif' title='XSS3' width='' alt='' />
  - [x] Steps to recreate: 
    - Create new video format post 
    - insert code ```[embed src='https://youtube.com/embed/123\x3csvg onload=alert(123)\x3e'][/embed]``` 
    - shows 123 when you view it
  - [x] Affected source code:
    - [Link 4](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)

## Assets

List any additional assets, such as scripts or files
N/A

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work:
N/A

## License

    Copyright [2022] [Shreyass Prem Sankar]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
