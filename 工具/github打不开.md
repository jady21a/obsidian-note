	
更改host
https://github.com.ipaddress.com/           ![[Pasted image 20220303180128.png]]

140.82.112.4
140.82.113.3 github.com 
13.229.188.59 github.com




https://fastly.net.ipaddress.com/github.global.ssl.fastly.net
![[Pasted image 20220303180140.png]]
https://github.com.ipaddress.com/assets-cdn.github.com
![[Pasted image 20220303180150.png]]
![[Pasted image 20220303180209.png]]
140.82.113.3 github.com  
199.232.69.194 github.global.ssl.fastly.net  
185.199.108.153 assets-cdn.github.com  
185.199.109.153 assets-cdn.github.com  
185.199.110.153 assets-cdn.github.com

win+x   cmd

 ipconfig /flushdns


![[Pasted image 20220303180313.png]]

host地址：C:\Windows\System32\drivers\etc

修改host todo   
属性  安全  高级 高级  更改权限  添加  选择主体   高级   立即查找  确定
![[Pasted image 20220303181318.png]]

![[Pasted image 20220303181804.png]]
		确定    确定


代理设置
对 github 进行局部代理
git config --global http. https://github.com.proxy=http://127.0.0.1:1080
git config --global https. https://github.com.proxy=https://127.0.0.1:1080

查看已有配置
git config --global -l
