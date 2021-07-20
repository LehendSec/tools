# nmap使用

#### -sS

```
当使用-sS选项进行扫描时,此时nmap会通过发送SYN包进行端口开放探测

(a)如果端口未开放,此时会返回ACK+RST

(b)如果端口开放,此时服务器会返回ACK+SYN的包,然后nmap在接收到SYN+ACK包后，会返回一个RST

 nmap为啥要返回一个RST的包而不是一个三次握手最后一步的ACK的包?
一般来说，只要完成三次握手,往往在服务器中都会留下日志痕迹,而如果未完成三次握手，则可能不被记录日志
```

**当使用-sS选项进行扫描时,此时nmap会通过发送SYN包进行端口开放探查**

![](./nmapImage\wps1.jpg) 

```
ip.addr == 192.168.1.41 && ip.addr == 192.168.1.166&&tcp.port==3306
```



![](./nmapImage\wps2.jpg) 

 

#### -sT

```
 对于-ST来说，如果端口未开放，与-SS保持一致,而如果端口开放，则-sT会完成一个完整的三次握手
 
nmap会通过发送SYN包进行端口开放探测

(a)如果端口未开放,此时会返回ACK+RST

(b)如果端口开放,此时服务器会返回SYN+ACK的包,然后nmap在接收到SYN+ACK包后，会返回一个ACK
```

![](./nmapImage\wps3.jpg) 

```
ip.addr == 192.168.1.41 && ip.addr == 192.168.1.166&&tcp.port==3306
```

![](./nmapImage\wps4.jpg)  

#### --sU(udp是无状态协议)

**为什么进行udp扫描时往往结果会随着网络的变化产生很大的差别?**

```
网络阻塞导致回包丢失

在udp扫描中，如果端口是未开放的它会返回一个端口不可达

对于udp端口来说，如果该端口开放,则可以直接不返回包

但是，如果探测服务器有防火墙则会直接丢掉发往该端口的包，此时对于nmap来说，就无法判断目标对应端口是否开放
```

![](./nmapImage\wps5.jpg) 

nmap -sU -p 3306 192.168.1.41

![](./nmapImage\wps6.jpg) 

 

-sU

ip.addr == 192.168.1.41 && ip.addr == 192.168.1.166&&udp.port==3306

![](./nmapImage\wps7.jpg) 

 

#### -sN

```
(null,扫描  发送畸形数据包) 某种情况可以绕waf(现在几乎不可能)
```

![](./nmapImage\wps8.jpg) 

 

#### -O 

```
探测操作系统类型

nmap -sS -O 192.168.1.14
```

![](./nmapImage\wps9.jpg) 

#### -sP

```
会首先发送一个icmp数据包然后再进行探测
```



#### -P0/-Pn 

```
nmap默认情况下，在进行端口扫描之前会默认发送一个icmp ping包，ping目标服务器以此来判断目标服务器是否存活，如果目标主机不存活，就不再进行对应的端口扫描。

现在有很多的防火墙会自动将ping请求的包给drop掉,所以这样目标服务器表现起来就像是一台不存活主机

无ping扫描(在服务器禁ping的情况下)

不会发送ICMP包，直接发送syn
```

nmap -Pn 192.168.1.14

![](./nmapImage\wps10.jpg) 

 

#### -p 指定端口

nmap -p- 192.168.1.14 / nmap -p 1-65535 192.168.1.14

![](./nmapImage\wps11.jpg) 

#### -sV 

```
探测具体版本号

nmap -sV 192.168.1.14 默认扫描1000个常用端口

nmap -sV -p- 192.168.1.14 扫描全端口
```



![](./nmapImage\wps12.jpg) 

![](./nmapImage\wps13.jpg) 

 

#### -A -T4 

全面扫描，等价于  -O -sV --script

nmap -A 192.168.1.14

-T 0-5 扫描

 

![](./nmapImage\wps14.jpg) 



#### -oA 

默认生成的结果会有三种类型后缀的文件

nmap -sV -oA bb 192.168.1.14 bb表示文件名称

 

nmap -sV -oX aa 192.168.1.14  aa表示文件名称

![](./nmapImage\wps15.jpg) 

![](./nmapImage\wps16.jpg) 

生成xml文件

![](./nmapImage\wps17.jpg) 

#### -sA  

```
ACK扫描，这项高级的扫描方法通常可以用来穿过防火墙
```

**nmap -sA 192.168.1.14**

![](./nmapImage\wps18.jpg) 

![](./nmapImage\wps19.jpg) 

#### -sW

 滑动窗口扫描

https://blog.csdn.net/wdscq1234/article/details/52444277

#### -V

 查看扫描过程进度

#### -S、-e

```
伪造源ip地址，一般和-e 一起使用 -e用于指定网卡

nmap -e eth0 -S 192.168.1.250 -sS -p- 192.168.1.14
```

![](./nmapImage\wps20.jpg) 

ip.addr == 192.168.1.14 && ip.addr == 192.168.1.250

![](./nmapImage\wps21.jpg) 

#### -g 

```
伪造源端口
nmap -g 80 -sS -p- 192.168.1.14

ip.addr == 192.168.1.14 && ip.addr == 192.168.1.166
```

![](./nmapImage\wps22.jpg) 

![](./nmapImage\wps23.jpg) 

####  --script=vuln

```
检查是否存在常见漏洞
```

####  --script=default/--sC

```
默认的脚本扫描，主要是搜集各种应用服务的信息
```



nmap -sS -p 1-10000 ip

nmap -sU -p- xxx.xxx.xx.0/24

nmap -e eth0 -S ip -g 80 -p- ip2

nmap -oA result -p- ip 

nmap -sV -O -p- ip