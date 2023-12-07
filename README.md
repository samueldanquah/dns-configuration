<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="DNS Configuration Exercises"/>
</p>

<h1>DNS Configuration Exercises in Azure Environment</h1>
This tutorial demonstrates practical exercises in managing DNS settings within an Azure-based Active Directory environment.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Active Directory Domain Services
- DNS Management
- Command-Line Tools

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Exercise Objectives</h2>

- A-Record Configuration
- Local DNS Cache Management
- CNAME Record Creation

<h2>Exercise Steps and Observations</h2>

<h3>A-Record Exercise:</h3>
<ul>
    <li>Logged into DC-1 as domain admin (mydomain.com\jane_admin).</li>
    <li>Logged into Client-1 as an admin (mydomain\jane_admin).</li>
    <li>Attempted to ping "mainframe" from Client-1, which initially failed.</li>
    <li>Used nslookup on "mainframe" from Client-1, observed failure due to no DNS record.</li>
    <li>Created a DNS A-record on DC-1 for “mainframe” pointing to DC-1’s Private IP address.</li>
    <li>Successfully pinged "mainframe" from Client-1 after A-record creation.</li>
</ul>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="A-Record Setup"/>
</p>
<p>
    This exercise demonstrated the importance and impact of A-records in DNS resolution.
</p>
<br />

<h3>Local DNS Cache Exercise:</h3>
<ul>
    <li>Changed mainframe’s record address to 8.8.8.8 on DC-1.</li>
    <li>Pinging "mainframe" from Client-1 still resolved to the old address due to local DNS cache.</li>
    <li>Checked local DNS cache with "ipconfig /displaydns" on Client-1.</li>
    <li>Flushed the DNS cache using "ipconfig /flushdns" on Client-1, observed an empty cache.</li>
    <li>Pinging "mainframe" again showed the address of the new record.</li>
</ul>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Local DNS Cache Management"/>
</p>
<p>
    This exercise highlighted how local DNS cache can affect DNS resolution and the importance of cache management.
</p>
<br />

<h3>CNAME Record Exercise:</h3>
<ul>
    <li>Created a CNAME record on DC-1 pointing “search” to “www.google.com”.</li>
    <li>Attempted to ping “search” from Client-1, observing the results of the CNAME record.</li>
    <li>Used nslookup on “search” from Client-1 to observe the results of the CNAME record.</li>
</ul>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="CNAME Record Configuration"/>
</p>
<p>
    The CNAME record exercise demonstrated how to redirect a host name to another domain name using DNS.
</p>
<br />

<!-- Footer or additional notes -->

