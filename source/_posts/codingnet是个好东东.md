title: coding.net是个好东东
date: 2014-08-30 15:57:26
tags: [折腾,git]
---
前几天发现有个垃圾站的域名是xxx.coding.net,当时还闪了一下怎么垃圾站的域名都这么高大上了.也没多长个心眼去看看顶级域名是什么情况.

直到昨天上班遇到一个需求,把一个php做的demo放到外网,我去找免费php空间的时候又一次搜到了这个神奇的网站.

经过我近一天的使用,感觉`coding.net`是想做成中国的github,同样可以建立远程git库,可以clone别人的git库,可以fork...等等等等.但是这货比github强在它的演示空间居然提供php环境(github.io只提供静态空间)!只需要简单的把本地的工程push到云端,配置好数据库,再切换到`演示`面板,点击`部署`就不用管了..实测访问速度超过某些号称高速的vps(服务器在国内就是好).

![coding.net演示界面截图](http://stariveer.qiniudn.com/blog/140830/140830_coding.net.jpg)

`coding.net`不支持github.io的自动部署,每次push代码之后需要手动点一下`一键部署`.

目前`coding.net`还不支持绑定域名,只能用它提供的二级域名.估计以后也不会提供绑定域名吧,那样的话建站蝗虫大军就该找它了.

---

顺便放上最近做的一个项目的前端demo
<div style="text-align:center">
    <iframe src="http://o2o-demo.coding.io/demo.php" frameborder="0" style="width:387px;height:783px;margin:0 auto;"></iframe>
</div>
fork me on [coding.net](https://coding.net/stariveer/O2O_demo.git).

Over
