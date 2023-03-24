![Group 12 1](https://user-images.githubusercontent.com/87405522/227531251-7d06c935-c4e6-4aca-80c2-e4b72d7e340f.png)
<section id="intro">
<h1>How to configure DNS in to client server network in vmware (part 3)</h1> <a href="#Videos">go to video</a>
</section>
<section id="body">
  <h2>What is DNS</h2>
  DNS stands for Domain Name System, and a DNS server is a computer server that contains a database of IP addresses and domain names. When you type a domain name into your web browser, your computer sends a request to a DNS server to look up the IP address associated with that domain name. The DNS server then returns the IP address to your computer, allowing it to connect to the website you requested.

In simpler terms, DNS servers are like the phone book of the internet. They translate human-friendly domain names, such as www.example.com, into machine-friendly IP addresses, such as 192.168.1.1, that are used to identify web servers and other network resources. Without DNS servers, we would have to remember and enter long strings of numbers to access websites and other online services.
</section>

<h2>Current Configuration
</h2>

<table>
<tr>
<td rowspan="4">Client </td>
</tr>
<tr><td>OS</td>
<td>Fedora 37</td>
</tr>
<tr>
<td>Netword Adaptors</td>
<td>VmNet 2</td>
</tr>
<tr>
<td>IP</td>
<td>Automatic (DHCP)</td>
</tr>
<tr>
<td rowspan="4">
Server
</td>
</tr>
<tr>
<td>OS</td>
<td>Cent Os 7</td>
</tr>
<tr>
<td>Network Adaptors</td>
<td>NAT + VmNet2</td>
</tr>
<tr>
<td>IP</td>
<td>10.0.1.2</td>
</tr>
<tr>
<td rowspan="4">VmNet2</td>
</tr>
<tr>
<td>IP</td>
<td>10.0.1.0</td>
</tr>
<tr>
<td>Net Mask</td>
<td>255.255.255.0</td>
</tr>
<tr>
<td>Type</td>
<td>Host Only</td>
</tr>
</table>


<h2>Cheat Sheet</h2>
<h3>Check host name</h3>

```
hostname -s
```

<h3>Check the domain name</h3>

```
hostname -d
```

<h3>Check the full qualified domain name </h3>

```
hostname --fqdn
```

<h3> change the HostName </h3>

```
nmtui
```
and then navigate to Set system hostname and chnage it.

```
mlb-dlc-centos7.ndm.lk
```

after you changing the host name you can type 

```
systemctl restart systemd-hostnamed
```

then to check whether the changers are hapend you can user (please copy only the command)
```
//command_one
hostname
//comand_two
cat /etc/hostname
//comand_three
cat /etc/sysconfig/network
```
![carbon (1)](https://user-images.githubusercontent.com/87405522/227563182-b3fce40d-51b2-470b-8977-8333f5d63c16.png)

<h3>Edit the hosts file</h3>

```
vi /etc/host
```

in that file add bellow the current context

```
10.0.1.2   mlb-dcl-centos7.ndm.lk
```

<h3>Reboot the system</h3>

```
reboot
```

<h3>Stop Other services</h3>

```
service <service_name> stop
```
you can replace <service_name> with dhcpd
<h3>To confirm service is stop</h3>

```
systemctl status dhcpd
```
if actice : fail or inactive(dead) then your good to go.

<h3>install DNS</h3>

```
yum install -y bind*
```

<h3>start the DNS</h3>
 
 ```
 service named start
 ```
 
 <h3> To check the status of the DNS </h3>
 
 ```
 service named status
 ```
 
<section id="Videos">
  <h2>Videos </h2>
  <ul>
    <li><a href="#">How to configure DNS in to client server network in vmware (part 3)</a></li>
    <li><a href="https://youtu.be/cpVDUaY2iSk">How to configure DHCP in to client server network in vmware (part 2)</a></li>
    <li><a href="https://youtu.be/HVKu4zFpjA0"> How to create Client-Server network using VMware (Part 1)</a></li>
  </ul>
  
   
   
     
    

 
</section>
