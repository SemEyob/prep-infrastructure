

<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1 align="center">Deploying On-Premises Active Directory in the Cloud (Azure)</h1>

<p>This home lab demonstrates how to set up a Domain Controller (DC) and a Client Virtual Machine (VM) in Microsoft Azure. It includes creating network resources, configuring <code>DC-1</code> with a static IP, disabling its firewall, and setting up <code>Client-1</code> to connect to <code>DC-1</code>. Connectivity is verified using <code>ping</code> and DNS tests.</p>



---

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop Protocol (RDP)</li>
  <li>Active Directory Domain Services</li>
  <li>PowerShell</li>
</ul>

<h2>Operating Systems Used</h2>
<ul>
  <li>Windows Server 2022</li>
  <li>Windows 10 (21H2)</li>
</ul>

<h2>Key Takeaways: Deploying On-Premises Active Directory in Azure</h2>

<ul>
  <li><strong>Proficiency with Cloud Platforms:</strong> Demonstrated ability to deploy and configure Active Directory in Microsoft Azure, including network setup and VM management.</li>
  <li><strong>DNS and Network Configuration:</strong> Successfully configured DNS settings and ensured seamless communication between domain controllers and clients.</li>
  <li><strong>Windows Server Expertise:</strong> Deployed and managed a Windows Server 2022 domain controller, showcasing skills in server administration and Active Directory setup.</li>
  <li><strong>Problem-Solving Skills:</strong> Verified connectivity and resolved potential issues using tools like PowerShell, <code>ping</code>, and <code>ipconfig</code>.</li>
  <li><strong>Hands-On Experience:</strong> Gained practical experience in creating and managing virtual environments that simulate on-premises Active Directory infrastructure.</li>
</ul>

---

<h2>High-Level Deployment and Configuration Steps</h2>

<h3>1. Setting Up the Domain Controller in Azure</h3>
<ol>
  <li>Create a Resource Group.</li>
  <li>Create a Virtual Network and Subnet.</li>
  <li>Create the Domain Controller VM (Windows Server 2022) named <code>DC-1</code>:</li>
  <ul>
    <li>Username: <code>labuser</code></li>
    <li>Password: <code>Cyberlab123!</code></li>
  </ul>
  <li>Set the Domain Controller’s NIC Private IP address to be static.</li>
  <li>Log into <code>DC-1</code> and disable the Windows Firewall (for testing connectivity).</li>
</ol>

<p align="center">
  <img src="https://github.com/user-attachments/assets/92697741-60f8-439d-9c74-1cc8fd16f916" alt="Domain Controller VM Screenshot" />
</p>

<h3>2. Setting Up Client-1 in Azure</h3>
<ol>
  <li>Create the Client VM (Windows 10) named <code>Client-1</code>:</li>
  <ul>
    <li>Username: <code>labuser</code></li>
    <li>Password: <code>Cyberlab123!</code></li>
  </ul>
  <li>Attach <code>Client-1</code> to the same region and Virtual Network as <code>DC-1</code>.</li>
  <li>Configure <code>Client-1</code>’s DNS settings to use <code>DC-1</code>’s Private IP address.</li>
</ol>

<p align="center">
  <img src="https://github.com/user-attachments/assets/830525e9-dfdd-4f3a-9793-740b4698779b" alt="Client-1 VM Screenshot" />
</p>

<h3>3. Testing Connectivity</h3>
<ol>
  <li>Restart <code>Client-1</code> from the Azure Portal.</li>
  <li>Log into <code>Client-1</code>.</li>
  <li>Ping <code>DC-1</code>’s private IP address to ensure connectivity:</li>
  <ul>
    <li>Confirm the ping succeeds.</li>
  </ul>
  <li>Open PowerShell on <code>Client-1</code> and run <code>ipconfig /all</code>:</li>
  <ul>
    <li>Verify the DNS settings show <code>DC-1</code>’s Private IP address.</li>
  </ul>
</ol>

<p align="center">
  <img src="https://github.com/user-attachments/assets/492b953e-6841-4d60-a19d-b5cbeab62683" alt="PowerShell Output Screenshot" />
</p>

---


