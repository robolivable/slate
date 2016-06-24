#### Hardware Requirements for Cloudant on Bluemix Local
Before you install Cloudant® on Bluemix Local, confirm that your system meets these requirements. The requirements include hardware, cluster,  requirements, Cloudant virtual machine distribution and physical host recommendations, and Logmet hardware requirements for installing the product.


[
            Page.new('Overview', 'index.html', [
              Page.new('Contents', 'index.html#contents', []),
              Page.new('Contribute', 'index.html#contribute', [])
            ]),
            Page.new('Cloudant Basics', 'basics.html', [
              Page.new('Database as a Service', 'basics.html#database-as-a-service', []),
              Page.new('IBM Bluemix', 'basics.html#ibm-bluemix', []),
              Page.new('HTTP API', 'basics.html#http-api', []),
              Page.new('JSON', 'basics.html#json', []),
              Page.new('How do I find data?', 'basics.html#how-do-i-find-data?', []),
              Page.new('Distributed', 'basics.html#distributed', []),
              Page.new('Replication', 'basics.html#replication', []),
            ]),
              Page.new('Versions of Cloudant', 'versions_cloudant.html#versions-cloudant', [
              	Page.new('Cloudant Local', 'cloudant_local.html#cloudant-local', []),
              	Page.new('Cloudant on Bluemix Local', 'cloudant_bluemix_local.html#cloudant-bluemix-local', [])
            ]),
            Page.new('Client Libraries', 'libraries.html', [
              Page.new('Supported', 'libraries.html#supported-client-libraries', []),
              Page.new('Third party', 'libraries.html#third-party-client-libraries', [])
            ]),
            Page.new('API Reference', 'api.html', [
              Page.new('HTTP', 'http.html', []),
              Page.new('Account', 'account.html', []),
              Page.new('Authentication', 'authentication.html', []),
              Page.new('Authorization', 'authorization.html', []),
              Page.new('CORS', 'cors.html', []),
              Page.new('Databases', 'database.html', []),
              Page.new('Documents', 'document.html', []),
              Page.new('Attachments', 'attachments.html', []),
              Page.new('Query', 'cloudant_query.html', []),
              Page.new('Design Documents', 'design_documents.html', []),
              Page.new('Views (MapReduce)', 'creating_views.html', []),
              Page.new('Search', 'search.html', []),
              Page.new('Cloudant Geospatial', 'geo.html', []),
              Page.new('Replication', 'replication.html', []),
              Page.new('Advanced Replication', 'advanced_replication.html', []),
              Page.new('Active tasks', 'active_tasks.html', []),
              Page.new('Virtual hosts', 'vhosts.html', []),
              Page.new('Advanced', 'advanced.html', []),
              Page.new('Monitoring', 'monitoring.html', []),
              Page.new('Backup', 'backup.html', []),
              Page.new('Try it', 'try.html', [])
            ]),
            Page.new('Guides', 'guides.html', [
              Page.new('JSON', 'json.html', []),
              Page.new('Replication', 'replication_guide.html', []),
              Page.new('Managing tasks', 'managing_tasks.html', []),
              Page.new('Document versioning and conflicts', 'mvcc.html', []),
              Page.new('Grouping related documents together in Cloudant', 'transactions.html', []),
              Page.new('CAP theorem', 'cap_theorem.html', []),
              Page.new('AcID', 'acid.html', []),
              Page.new('Backup', 'backup-guide.html', []),
              Page.new('Backup using Replication', 'backup-guide-using-replication.html', []),
              Page.new('CouchApps', 'couchapps.html', []),
              Page.new('Design document management', 'design_document_management.html', [])
            ])
          ].








##### Operating system
Cloudant uses Debian version 8 operating system exclusively.

##### Clusters
Cloudant in Bluemix Local requires two clusters minimum. One cluster internally
powers the Bluemix platform, while the other cluster powers external customer accounts and data.

#####Hardware requirements	
 
<table>
<tr>
<th>Type</th>
<th>Count</th>
<th>Optional?</th>
<th>Name format</th>
<th>min vCPU</th>
<th>recommended vCPU</th>
<th>min RAM (GB)</th>
<th>recommended RAM (GB)</th>
<th>Disk-OS (GB)</th>
<th>Disk Config - OS</th>
<th>min Disk - Data (GB)</th>
<th>recommended min Disk - Data (GB)</th>
<th>Disk Config - Data</th>
<th>Network (Gbps)</th>
</tr>

<tr>
<td>Infra</td>
<td>1</td>
<td>No</td>
<td>infra1.bml-<customer></td>
<td>8</td>
<td>8</td>
<td>16</td>
<td>16</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>3000</td>
<td>3000</td>
<td>VMDK - thin/independent persistent</td>
<td>1</td>
</tr>

<tr>
<td>SAPI</td>
<td>2</td>
<td>No</td>
<td>sapi<#>.bml-<customer></td>
<td>4</td>
<td>4</td>
<td>4</td>
<td>4</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>1</td>
</tr>

<tr>
<td>Load Balancer (Bluemix Ops Cluster)</td>
<td>2</td>
<td>No</td>
<td>lb<#>.bml-ops-<customer>001</td>
<td>8</td>
<td>8</td>
<td>8</td>
<td>8</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>1</td>
</tr>

<tr>
<td>Load Balancer (Customer Cluster)</td>
<td>2</td>
<td>No</td>
<td>lb<#>.bml-<customer>001</td>
<td>8</td>
<td>8</td>
<td>8</td>
<td>8</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>1</td>
</tr>

<tr>
<td>DB Node (Bluemix Ops Cluster)</td>
<td>3</td>
<td>No</td>
<td>db<#>.bml-ops-<customer>001</td>
<td>8</td>
<td>8</td>
<td>16</td>
<td>16</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>800</td>
<td>800</td>
<td>VMDK - thick eager-zeroed / independent persistent</td>
<td>1</td>
</tr>

<tr>
<td>DB Node (Customer Cluster) </td>
<td>3</td>
<td>No</td>
<td>db<#>.bml-<customer>001</td>
<td>8</td>
<td>48</td>
<td>16</td>
<td>64</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>800</td>
<td>1000</td>
<td>VMDK - thick eager-zeroed/independent persistent</td>
<td>1</td>
</tr>

<tr>
<td>Load Balancer (Backup Cluster)</td>
<td>2</td>
<td>Yes</td>
<td>lb<#>.bml-<customer>-bk001</td>
<td>8</td>
<td>8</td>
<td>8</td>
<td>8</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>1</td>
</tr>

<tr>
<td>DB Node (Backup Cluster)</td>
<td>3</td>
<td>Yes</td>
<td>db<#>.bml-<customer>-bk001</td>
<td>8</td>
<td>24</td>
<td>16</td>
<td>64</td>
<td>10</td>
<td>VMDK - thick eager-zeroed</td>
<td>800</td>
<td>18000</td>
<td>VMDK - thin/independent persistent</td>
<td>1</td>
</tr>

</table>

###### Logmet hardware requirements							
<table>
<tr>
<th>Type</th>
<th>Count</th>
<th>Optional?</th>
<th>min vCPU</th>
<th>recommended vCPU</th>
<th>min RAM (GB)</th>
<th>recommended RAM (GB)</th>
<th>min Disk (GB)</th>
<th>recommended Disk (GB)</th>
</tr>
<tr>
<td>Logmet Core</td>
<td>3</td>
<td>No</td>
<td>4</td>
<td>4</td>
<td>20</td>
<td>20</td>
<td>900</td>
<td>900</td>
</tr>
<tr><td>Logmet HAProxy
</td>
<td>2</td>
<td>No</td>
<td>1</td>
<td>1</td>
<td>4</td>
<td>4</td>
<td>40</td>
<td>40</td></tr>
<tr>
<td>Logmet Manager
</td>
<td>1</td>
<td>No</td>
<td>1</td>
<td>1</td>
<td>4</td>
<td>4</td>
<td>40</td>
<td>40</td></tr>
<tr><td>Logmet Expansion
</td>
<td>3</td>
<td>Yes</td>
<td>3</td>
<td>3</td>
<td>12</td>
<td>12</td>
<td>600</td>
<td>600</td>
</tr>
<td>CFS Ops
</td>
<td>1</td>
<td>No</td>
<td>2</td>
<td>2</td>
<td>8</td>
<td>8</td>
<td>350</td>
<td>350</td>
</tr>
</table>

##### Cloudant virtual machine distribution and physical host recommendations			
These recommendations assume that you are using the recommended hardware outlined above as well as using a backup cluster.		

<table>
<tr>
<th>Host</th>
<th>vCPU</th>
<th>RAM used</th>
<th>VMs deployed</th>
</tr>

<tr><td>1</td>
<td>48</td>
<td>64</td>
<td>db1.bml-<customer>001</td>
</tr>
<tr><td>2</td>
<td>48</td>
<td>64</td>
<td>db2.bml-<customer>001</td>
</tr>
<tr><td>3</td>
<td>48</td>
<td>64</td>
<td>db3.bml-<customer>001</td>
</tr>
<tr><td>4</td>
<td>48</td>
<td>96</td>
<td>lb1.bml-<customer>001
lb1.bml-ops-<customer>001
db1.bml-ops-<customer>001
db1.bml-<customer>-bk0011</td>
</tr>
<tr><td>5</td>
<td>48</td>
<td>96</td>
<td>lb2.bml-<customer>001
lb2.bml-ops-<customer>001
db2.bml-ops-<customer>001
db2.bml-<customer>-bk0011</td>
</tr>
<tr><td>6</td>
<td>44</td>
<td>92</td>
<td>lb1.bml-<customer>-bk001
db3.bml-ops-<customer>001
db3.bml-<customer>-bk001
sapi1.bml-<customer></td>
</tr>
<tr><td>7</td>
<td>20</td>
<td>38</td>
<td>lb2.bml-<customer>-bk001
sapi2.bml-customer
infra1.bml-customer</td>
</tr>
</table>

##### Virtual machine requirements
In order to ensure the highest possible performance for your database deployment, Cloudant requires that each virtual machine meet the following specifications.  

*	Set up VMs using a thick provision eager zeroed disk.
*	Configure the infra-auxiliary VM and the three data partitions for the backup database VMs using thin provisioning.

This configuration equals 7 TB thick and 21 TB thin virtual disks. Initially, you must prepare to use 8 TB virtual disk space out of the box.

###### Supported VMware versions
Cloudant on Bluemix Local supports VMware versions 5.5 an 6.0. 

##### Network requirements for Cloudant
Set the maximum transmission unit (MTU) value to 9000 for virtual switches.

##### External internet access requirement 
External internet access is required. However, there is no need to make any networking changes. The Cloudant initial architecture design routes external internet traffic to pypi, rubygems, github, and dynect through the tether. Future versions will pull all dependencies in to the local deployment, eliminating this requirement.