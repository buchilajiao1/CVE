# XSS exists in Xunrui CMS v4.6.3 and below

## CVE-ID : 
CVE-2024-31634

## Vulnerability Type : 
Stored XSS

## Vulnerability Version :
Xunruicms<=v4.6.3

## Recurring environment
* Windows 11  
* PHP 7.4.3  
* Nginx 1.15.11

## Vulnerability Description AND recurrence:
(1) There is a filter for xss in the Security.php file in the catalog \XunRuiCMS\dayrui\Fcms\Library\.
![1](./1.png)

But it only filters for normal xss scripts.
(2) Local environment can be found in the login situation of the user-agent filtering
![4](./4.png)

(3) The packet in the backend login screen is tested with a mutated xss payload:
`User-Agent:"><svg/onload=alert(1)//`
![6](./6.png)
![2](./2.png)

(4) Go to background profile modification->login record, and found that triggering storage shape XSS
![5](./5.png)

![3](./3.png)
