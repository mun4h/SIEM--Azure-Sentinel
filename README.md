<h1>SIEM demonstartion using Azure Sentinel</h1>


<h2>Description</h2>
This Project shows a simple demonstration of an SIEM setup using Azure Sentinel and a vulnerable virtual machine in the cloud and subsequently a map of live attacks on the machine machine
<br />

<h2>Environments Used </h2>
- <b>Microsoft Azure <a href="https://azure.microsoft.com/en-us/free/">here</a> </b>

<h2>Lab walk-through:</h2>

<h3>Sign up for a free account with either a Microsoft account or a GitHub account, this will require a credit card to get $200 free worth of service for 12 months </h3>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/1.png" height="30%" width="80%"/>

<h3>Once account is set up, go to <a href="https://portal.azure.com/">Azure Portal</a> </h3>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/2.png" height="30%" width="80%"/>

<h3>Create a Virtual Machine also known as a honeypot that will be exposed to the internet and allow anyone from any part of the world to try to access it once they see it available on the internet</h3>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/3.png" height="30%" width="80%"/>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/4.png" height="300%" width="80%"/>

<h3>Set up the Virtual Machine by creating a new resource group for resource share and everything in this lab will be put in this resource group</h3>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/5.png" height="30%" width="80%"/>

<h3> Create a name for the Virtual machine, add the region, and leave other options as default, then create a user and password for the VM</h3>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/6.png" height="30%" width="80%"/>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/7.png" height="30%" width="80%"/>

<h3>Confirm the licensing information and click Next to Disks and Next to Networking </h3>

<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/8.png" height="30%" width="80%"/>

<h3>Create a new firewall control, make it open to the internet, remove the default rule, and create a new inbound rule that allows everything into the VM </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/9.png" height="30%" width="80%"/>
<h3>Change the destination port to * for any  and make the priority to a low value and name the rule which will allow all traffic from the internet into the VM this rule will allow the VM to be discoverable </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/10.png" height="30%" width="80%"/>

<h3> Click Review and Create once the new rule has been added then on the next page, click Create </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/11.png" height="30%" width="80%"/>

<h3> The deployment is done and VM has been set up </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/12.png" height="30%" width="80%"/>

<h3> Next is to make log Analytics workspaces that will be used to inject logs from the VM and we will also create a custom log that contains geographic information of where the attacks are coming from </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/13.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/14.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/15.png" height="30%" width="80%"/>
<h3>Azure sentinel will connect to the workspace to display the geodata on the map</h3>
<h3> Click Review and Create, then click Create on the next page </h3>
<h3>Set up a Security Center also known as Microsoft Defender for Cloud and enable the ability to gather logs from the VM into the Log Analytics Workspaces</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/16.png" height="30%" width="80%"/>
<h3> Then go to Management, Environment settings, and select the workspace under Azure subcriptions</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/17.png" height="30%" width="80%"/>
<h3>Turn off the SQL server and save at the top</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/18.png" height="30%" width="80%"/>
<h3>Go to log analytics workspaces and connect to the virtual machine </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/19.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/19b.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/19c.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/19d.png" height="30%" width="80%"/>
<h3>Set up Sentinel which is the SIEM to use to visualize the attack data and pick log analytics workspace to get logs from </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/20.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/20a.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/20b.png" height="30%" width="80%"/>
<h3>Go to virtual machines then to the VM create to get the public IP address</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/21.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/22.png" height="30%" width="80%"/>
<h3>Use the IP address and connect to the VM with RDP(remote desktop connection on the local machine</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/22a.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/22b.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/22c.png" height="30%" width="80%"/>
<h3>Logging in to the VM with incorrect credentials to get the log from the Event Viewer on the VM</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/23a.png" height="30%" width="80%"/>
<h3>Going through the details of the failed login attempt will give the username, failure reason, and IP address of the attempt   </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/23.png" height="30%" width="80%"/>
<h3><b>Go to the IP geolocation website to get more information about the attempted login using the IP address <a href="https://ipgeolocation.io/">here</a> </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/24.png" height="30%" width="80%"/>
<h4> Use the log in the result to create a custom log and send the log to the log analytics workspace and use the Azure sentinel to read the information and use it to plot a map </h4>
<h3>Turn the firewall off on the VM to allow any inbound ECHO request and make it available on the internet faster</h3>
<h3>Ping the VM with the IP address before and after turning off the firewall</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/25.png" height="30%" width="80%"/>
<h3>Open a new script of Windows Powershell ISE and Copy/paste a script that will be used to filter failed RDP events from Windows Event Viewer/h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/26.png" height="30%" width="80%"/>
 <img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/27.png" height="30%" width="80%"/>
<h3>Save the pasted script on desktop</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/27a.png" height="30%" width="80%"/>
<h3> Sign up on IPGeolocation website to get the API KEY <a href="https://ipgeolocation.io/">here</a></h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/28.png" height="30%" width="80%"/>
<h3>Sign up with Google or sign up with an email </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/28a.png" height="30%" width="80%"/>
<h3>Sign up on the website will give the ability to get geodata and longitude &latitude </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/28b.png" height="30%" width="80%"/>
<h3>Paste the API key in the script and run the script</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/28c.png" height="30%" width="80%"/>
<h3>The script output will save the log in this C drive</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/28d.png" height="30%" width="80%"/>
<h3>Here is the location in the C drive named failed_rdp/h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/28e.png" height="30%" width="80%"/>
<h3>Run the script to show the output</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/29.png" height="30%" width="80%"/>
 <h3>The Script takes all failed login attempts from the Event viewer,  takes it to the IPgeolocation website, and shows the geo data  in the output section of the powershell</h3>
 <img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/31.png" height="30%" width="80%"/>
<h3>Using the sample geo data in the log file on the C drive to train the log analytics workspaces to accept and parse out the custom log </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/30.png" height="30%" width="80%"/>
<h3>Go to Azure and create a custom log in the Log Analytics workspaces that will allow custom log with geodata from the IPgeolocation website  </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/32.png" height="30%" width="80%"/>
<h3>Go to the Log Analytics workspace, and select Tables, in the Tables blade, select New custom log (MMA-based) and set up the custom log</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/32a.png" height="30%" width="80%"/>
<h3>Copy the failedRDP log file to the local machine and open and select the file in the C drive on the local machine then click next</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/32b.png" height="30%" width="80%"/>
<h3>Click next on the next page and </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/32c.png" height="30%" width="80%"/>
<h3>On the next page, select the OS type and put the log path on the VM then go to the next page</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/32d.png" height="30%" width="80%"/>
<h3>Put a name and go to next to create the custom log</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/32e.png" height="30%" width="80%"/>
<h3>Run the custom log to query to show the failed RDP login</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/33.png" height="30%" width="80%"/>
<h3>We will use the script to extract raw data from the query result to make different fields </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/34.png" height="30%" width="80%"/>
<h3>Setting up a map in sentinel by going to the Log Analytics workspace and setting up a new workbook</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/35a.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/35b.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/35c.png" height="30%" width="80%"/>
<h3>Edit the workbook by removing the default widgets</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/35d.png" height="30%" width="80%"/>
 <h3>Add a new query</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/35e.png" height="30%" width="80%"/>
<h3>Add a new query and run </h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/36.png" height="30%" width="80%"/>
<h3>Change the visualization to map</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/37.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/37a.png" height="30%" width="80%"/>
<h3>Change the metric label to "Country" to show the number of attacks coming from different countries</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/37b.png" height="30%" width="80%"/>
<h3>Click "done editing" and save</h3>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/37c.png" height="30%" width="80%"/>
<img src="https://github.com/mun4h/SIEM--Azure-Sentinel/blob/main/images/37d.png" height="30%" width="80%"/>





















<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
