	
# 更改 host

https://github.com.ipaddress.com/           

140.82.112.4
140.82.113.3 github.com 
13.229.188.59 github.com

https://fastly.net.ipaddress.com/github.global.ssl.fastly.net

https://github.com.ipaddress.com/assets-cdn.github.com


140.82.113.3 github.com  
199.232.69.194 github.global.ssl.fastly.net  
185.199.108.153 assets-cdn.github.com  
185.199.109.153 assets-cdn.github.com  
185.199.110.153 assets-cdn.github.com

## 刷新 dns
- win+x   cmd
- ipconfig /flushdns

## host 地址：C:\Windows\System32\drivers\etc

## 修改 host todo   
属性  安全  高级 高级  更改权限  添加  选择主体   高级   立即查找  确定
![[Pasted image 20220303181318.png]]

![[Pasted image 20220303181804.png]]
		确定    确定


# 自动更新 host
https://www.loganjin.cn/article/auto-update-hosts/ (未用) 

use：
https://github.com/ovenx/github-hosts

140.82.112.4 github.com
140.82.114.4 gist.github.com
185.199.111.153 assets-cdn.github.com
185.199.111.133 raw.githubusercontent.com
185.199.109.133 gist.githubusercontent.com
185.199.111.133 cloud.githubusercontent.com
185.199.111.133 camo.githubusercontent.com
185.199.108.133 avatars.githubusercontent.com
185.199.111.133 avatars0.githubusercontent.com
185.199.111.133 avatars1.githubusercontent.com
185.199.111.133 avatars2.githubusercontent.com
185.199.111.133 avatars3.githubusercontent.com
185.199.110.133 avatars4.githubusercontent.com
185.199.110.133 avatars5.githubusercontent.com
185.199.111.133 avatars6.githubusercontent.com
185.199.111.133 avatars7.githubusercontent.com
185.199.109.133 avatars8.githubusercontent.com
185.199.110.154 github.githubassets.com


# 代理设置
https://tding.top/archives/cbef72d4.html

对 github 进行局部代理
```
git config --global http.https://github.com.proxy https://127.0.0.1:1080  

git config --global https.https://github.com.proxy https://127.0.0.1:1080

```

取消代理
```
git config --global --unset http.proxy  
git config --global --unset https.proxy
```



全局代理
skip

查看已有配置
git config --global -l


---
