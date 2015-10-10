title: apache配置备忘
date: 2014-09-28 18:04:30
tags: [apache]
categories: [front-end]
---
举个栗子:
```
<Directory "/Users/HeXing/Sites">
    Options Indexes FollowSymLinks
    AllowOverride None
    Order allow,deny
    Allow from all
</Directory>
```
####Options Indexes FollowSymLinks
配置目录`/Users/HeXing/Sites`,如果你的文件根目录里有 index.html，浏览器就会显示 index.html的内容，如果没有 index.html，浏览器就会显示文件根目录的目录列表，目录列表包括文件根目录下的文件和子目录。要禁止 Apache 显示目录结构列表，只需将 Option 中的 Indexes 去掉即可。

####AllowOverride
在 `AllowOverride` 设置为 None 时， .htaccess 文件将被完全忽略。当此指令设置为 All 时，所有具有 ".htaccess" 作用域的指令都允许出现在 .htaccess 文件中。从安全性考虑，根目录的AllowOverride属性一般都配置成不允许任何Override,即`AllowOverride None`.

#####AllowOverride的参数：
**AuthConfig** 允许使用与认证授权相关的指令(AuthDBMGroupFile, AuthDBMUserFile, AuthGroupFile, AuthName, AuthType, AuthUserFile, Require等)。
**FileInfo** 允许使用控制文档类型的指令(DefaultType, ErrorDocument, ForceType, LanguagePriority, SetHandler, SetInputFilter, SetOutputFilter, mod_mime中的 Add 和 Remove 指令等等)、控制文档元数据的指令(Header, RequestHeader, SetEnvIf, SetEnvIfNoCase, BrowserMatch, CookieExpires, CookieDomain, CookieStyle, CookieTracking, CookieName)、mod_rewrite中的指令(RewriteEngine, RewriteOptions, RewriteBase, RewriteCond, RewriteRule)和mod_actions中的Action指令。

**Indexes** 允许使用控制目录索引的指令(AddDescription, AddIcon, AddIconByEncoding, AddIconByType, DefaultIcon, DirectoryIndex, FancyIndexing, HeaderName, IndexIgnore, IndexOptions, ReadmeName, 等)。

**Limit** 允许使用控制主机访问的指令(Allow, Deny, Order)。Options[=Option,...] 允许使用控制指定目录功能的指令(Options和XBitHack)。可以在等号后面附加一个逗号分隔的(无空格的)Options选项列表，用来控制允许Options指令使用哪些选项。

####Order Allow Deny
via [Fwolf's Blog][1]
**Allow**和**Deny**可以用于apache的conf文件或者.htaccess文件中（配合Directory, Location, Files等），用来控制目录和文件的访问授权。

所以，最常用的是：
```
Order Deny,Allow
Allow from All
```
注意“Deny,Allow”中间只有一个逗号，也只能有一个逗号，有空格都会出错；单词的大小写不限。上面设定的含义是先设定“先检查禁止设定，没有禁止的全部允许”，而第二句没有Deny，也就是没有禁止访问的设定，直接就是允许所有访问了。这个主要是用来确保或者覆盖上级目录的设置，开放所有内容的访问权。

按照上面的解释，下面的设定是无条件禁止访问：
```
Order Allow,Deny
Deny from All
```
如果要禁止部分内容的访问，其他的全部开放：
```
Order Deny,Allow
Deny from ip1 ip2
```
或者
```
Order Allow,Deny
Allow from all
Deny from ip1 ip2
```
apache会按照order决定最后使用哪一条规则，比如上面的第二种方式，虽然第二句allow允许了访问，但由于在order中allow不是最后规则，因此还需要看有没有deny规则，于是到了第三句，符合ip1和ip2的访问就被禁止了。注意，order决定的“最后”规则非常重要，下面是两个错误的例子和改正方式：
```
Order Deny,Allow
Allow from all
Deny from domain.org
```
错误：想禁止来自domain.org的访问，但是deny不是最后规则，apache在处理到第二句allow的时候就已经匹配成功，根本就不会去看第三句。 解决方法：Order Allow,Deny，后面两句不动，即可。
```
Order Allow,Deny
Allow from ip1
Deny from all
```
错误：想只允许来自ip1的访问，但是，虽然第二句中设定了allow规则，由于order中deny在后，所以会以第三句deny为准，而第三句的范围中又明显包含了ip1（all include ip1），所以所有的访问都被禁止了。 解决方法一：直接去掉第三句。 解决方法二：
```
Order Deny,Allow
Deny from all
Allow from ip1
```


[1]:http://www.fwolf.com/blog/post/191
