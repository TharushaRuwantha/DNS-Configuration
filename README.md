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

```ruby
hostname -s
```

<h3>Check the domain name</h3>

```ruby
hostname -d
```

<h3>Check the full qualified domain name </h3>

```ruby
hostname --fqdn
```

<h3> change the HostName </h3>

```ruby
nmtui
```
and then navigate to Set system hostname and chnage it.

```ruby
mlb-dlc-centos7.ndm.lk
```

after you changing the host name you can type 

```ruby
systemctl restart systemd-hostnamed
```

then to check whether the changers are hapend you can user 
```ruby
//command one
hostname
//comand two
cat /etc/hostname
//comand three
cat /etc/sysconfig/network
```

<section id="Videos">
  <h2>Videos </h2>
  <ul>
    <li><a href="#">How to configure DNS in to client server network in vmware (part 3)</a></li>
    <li><a href="https://youtu.be/cpVDUaY2iSk">How to configure DHCP in to client server network in vmware (part 2)</a></li>
    <li><a href="https://youtu.be/HVKu4zFpjA0"> How to create Client-Server network using VMware (Part 1)</a></li>
  </ul>
  
   
   
     
    

 
</section>
