1 A) Objective: Configure and use vCenter Server Appliance.
1. Access your vCenter Server Appliance and Configure Licenses.
2. Configure Single Sign-On and Create a Data Center Object.
3. Add Your ESXi Hosts to the vCenter Server Inventory.
4. Configure the ESXi Hosts as NTP Clients.
5. Create a Host and Cluster FolderIn the current lab configuration, no datastores have been
configured. Datastores are added in a later lab.
6. Create Virtual Machine and Template Folders.
7. Navigate vSphere Client.
Steps:
Task 1: Access your vCenter Server Appliance and Configure Licenses
You connect to the vSphere Client and license both vCenter Server and ESXi hosts.
1. In your Firefox Web browser, click vSphere Site-A on the favorite bar and select vSphere Client
(SA-VCSA-01).
2. Log in to vCenter Server with the user name administrator@vsphere.local and the password
VMware1!.
3. In vSphere Client, click the Menu icon and select Administration
4. In the Navigator pane, select Licenses.
5. In the Licenses pane, the Licenses tab is selected.
6. Click the Add New Licenses icon (the plus sign).
7. On the Enter license keys page, enter the vCenter Server and VMware vSphere® Enterprise Plus
Edition™ license keys provided by your instructor in the License keys text box.
You must enter the license keys on separate lines.
8. Verify that both licenses are listed correctly in the text box and click Next.
9. On the Edit license names page, enter VMware vCenter Server and VMware ESXi in the
appropriate License name text boxes.
10. Click Next.
11. On the Ready to complete page, click Finish.
12. In the Licenses pane, click the Assets tab.
13. Select the sa-vcsa-01.vclass.local check box and click Assign License.
14. In Assign License, select the updated vCenter Server license and click OK.
At the bottom of the Assign License page, the Some features will become unavailable
message appears.
15. Close the There are vCenter Server systems with expired or expiring licenses in your inventory
warning.

Task 2: Configure Single Sign-On and Create a Data Center Object
You edit the Single Sign-On (SSO) configuration and create a data center object.
1. In the Administration page, select Single Sign-On > Configuration.
2. On the Policies tab, verify that the Password Policy tab is open and click Edit.
3. In the Maximum lifetime text box, verify that 0 is entered for the password never expires value.
4. Click OK to save
5. Click the Menu icon and select Shortcuts.
6. In the Inventories pane, click Hosts and Clusters
7. In the Navigator pane, right-click sa-vcsa-01.vclass.local and select New Datacenter.
8. In the New Datacenter Name text box, enter SA-Datacenter and click OK.
In the Navigator pane, you should see that the new data center object is listed under vCenter Server
Appliance

Task 3: Add Your ESXi Hosts to the vCenter Server Inventory
You add ESXi hosts to the vCenter Server inventory.
1. In the Navigator pane, right-click SA-Datacenter and select Add Host.
The Add Host wizard appears.
2. On the Name and location page, enter sa-esxi-01.vclass.local and click Next.
3. On the Connection settings page, enter root as the user name, enter the password VMware1!, and
click Next.
4. If you see a security alert stating that the certificate store of vCenter Server cannot verify the
certificate, click Yes to proceed.
5. On the Host summary page, review the information and click Next.
6. On the Assign license page, click the VMware ESXi license key and click Next.
7. On the Lockdown mode page, accept the default Disabled and click Next.
8. On the VM location page, accept the default and click Next.
9. On the Ready to complete page, review the information and click Finish.
10. In the Recent Tasks pane, monitor the progress of the task.
11. Repeat steps 1 through 10 to add sa-esxi-02.vclass.local to the Navigator pane.
12. In the Navigator pane, expand SA-Datacenter.
13. In the Navigator pane, select sa-esxi-01.vclass.local.
The Summary tab opens in the right pane. This tab displays information for the ESXi host, such as
CPU, memory, storage, NICs, and virtual machines.
14. Click the arrow next to the Hardware pane to view the hardware details of the ESXi host.

Task 4: Configure the ESXi Hosts as NTP Clients
You configure the ESXi hosts to use Network Time Protocol (NTP) to maintain accurate time and date.
1. In the right pane, click the Configure tab.
When repeating steps for your second host, select sa-esxi-02.vclass.local from the Navigation pane.
2. Navigate to System in the middle pane, and select Time Configuration to view the current settings.
3. Click Edit.
4. Click Use Network Time Protocol (Enable NTP client).
5. In the NTP Servers text box, verify that 172.20.10.10 is entered.
6. Next to NTP Service Status, select the Start NTP Service check box.
7. From the NTP Service Startup Policy drop-down menu, select Start and stop with host.
8. Click OK.
9. In the Time Configuration pane, verify that the NTP client appears as Enabled and that the NTP
service status appears as Running.
10. Repeat steps 1 though 9 to configure your second ESXi host.
11. On the Summary tab of your second host, suppress the ESXi Shell enabled and SSH enabled
warnings. These warnings are present to alert you of the current host configuration.
In the current lab configuration, no datastores have been configured. Datastores are added in a later
lab.

Task 5: Create a Host and Cluster Folder
You create a folder to group hosts and clusters of the same type.
1. In the upper left-hand corner of vSphere Client, click vSphere Client.
The vSphere Client Shortcuts page opens.
2. Click Hosts and Clusters.
3. In the Navigator pane, right-click SA-Datacenter and select New Folder > New Host and Cluster
Folder.
4. In the Enter a name for the folder text box, enter Lab Servers and click OK.
5. Drag both the ESXi hosts to the Lab Servers folder.
6. In the Recent Tasks pane, monitor the Move Entities tasks until they are completed.

Task 6: Create Virtual Machine and Template Folders
You use folders to group virtual machines of the same type.
1. In vSphere Client, click the Menu icon and select VMs and Templates.
2. Right-click SA-Datacenter and select New Folder > New VM and Template Folder.
3. In the Enter a name for the folder text box, enter Lab VMs and click OK.
4. In the Navigator pane, expand the SA-Datacenter object.
5. Right click the Win10-Empty virtual machine.
6. In the Actions - Win10-Empty menu, click Delete from Disk.
7. In Confirm Delete, click Yes.
8. In the Navigator pane, drag the Win10-01 and Win10-02 virtual machines to the Lab VMs folder.
9. Expand the Lab VMs folder to verify that both virtual machines are in the folder.
10. Right-click SA-Datacenter and select New Folder > New VM and Template Folder to create a
second virtual machine folder.
11. In the Enter a name for the folder text box, enter Templates and click OK.
The Lab VMs and Templates folder that you created in this lab appears in the Navigator pane.
12. Right-click the Labs VMs folder and review the menu commands in the drop-down menu.
13. Click the Host and Clusters icon.
14. Right-click the Lab Servers folder and review the menu commands in the drop-down menu.

Task 7: Navigate vSphere Client
In VMware vSphere® Client™, you navigate through the objects in the navigation tree and view the
configuration settings to become familiar with the UI layout.
1. In the Navigator pane, click the arrow next to each object to expand the view completely.
2. In the Navigator pane, select sa-esxi-01.vclass.local.
3. In the right pane, review the Summary tab and record the following information.
a. Hypervisor
b. Logical Processors
c. NICs
4. On the Summary tab, expand the Hardware and Configuration panes to review the information.
5. In the Navigator pane, select sa-vcsa-01.vclass.local to return to the top of the navigation tree.
6. In the Search text box on the top, enter datastore.
7. When the datastores names appear under the search box, click Class-Datastore
8. On the Summary tab, review the datastore details in the Details pane.
9. In vSphere Client, Click the Menu icon and select Home.
10. Logout of vSphere Client and close the Firefox Web browser.
11. In the next lab, you use vSphere Web Client to perform the tasks.
12. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

(B) Aim: Assign roles and permissions to Active Directory users to perform functions in
vCenter Server Appliance.
Objective : In this lab, you perform the following tasks:
1. Join the vCenter Server Appliance to vclass.local Domain
2. Add vclass.local as an Identity Source
3. View Active Directory Users
4. Assign Object Permissions to an Active Directory User
5. Assign Root-Level Global Permission
6. Log In with Windows Session Authentication
7. Use an Active Directory User to Manage a Virtual Machine
In this lab, you use vSphere Web Client to perform the tasks
Steps:
Task 1: Join the vCenter Server Appliance to vclass.local Domain
You can configure a Platform Services Controller appliance or a vCenter Server Appliance with an
embedded Platform Services Controller to join or leave an Active Directory domain. Verify that the user
name you use to log in to the vCenter Server instance in the vCenter Server Appliance is a member of
the System Configuration. Administrators group in vCenter Single Sign-On.
In this lab you join VCSA to the vclass.local domain as an Active Directory (Integrated Windows
Authentication) Identity Source. This allows an active directory user to be selected and assigned rights
to manage a virtual machine.
1. Open your Firefox web browser, click vSphere Site-A on the favorite bar, and select vSphere Web
Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. In vSphere Web Client, click the Home icon and select Administration.
4. In the Administration pane, navigate to Deployment and select System Configuration.
5. Under System Configuration, select Nodes.
6. Under Nodes, select sa-vcsa-01.vclass.local, and click the Manage tab.
7. Under Advanced, select Active Directory, and click Join.
8. In the sa-vcsa-01.vclass.local Join Active Directory wizard, enter the following information.
  Domain vclass.local
  Organizational Unit Leave blank
  User name administrator@vclass.local
  Password VMware1!
9. Click OK.
You will not receive an acknowledgment message after clicking OK. Move to the next step.
10. Reboot the VCSA.
a. From the sa-vcsa-01.vclass.local Actions menu, and select Reboot.
b. In the sa-vcsa-01.vclass.local - Reboot dialog box, enter Joining sa-vcsa-01.vclass.local
to the vclass.local domain., and click OK.
The reboot takes 10 to 15 minutes.
11. Close vSphere Web Client.

Task 2: Add vclass.local as an Identity Source
1. Open the Firefox web browser, click vSphere Site-A on the favorite bar, and select vSphere Web
Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. In vSphere Web Client, click the Home icon, and select Administration.
4. In the Administration pane, navigate to Single Sign-on and select Configuration.
5. In the SSO Configuration for sa-vcsa-01.vclass.local pane, click the Identity Sources tab.
6. On the Identity Sources tab, click the Add Identity Source icon (the green plus sign).
The Add identity source wizard opens.
7. On the Select Identity Source Type page, verify that Active Directory (Integrated Windows
Authentication) is selected.
8. Click Next.
9. On the Configure Identity Source Type page, verify that VCLASS.LOCAL is entered in the
Domain name field.
10. Click Next.
11. On the Ready to Complete page, review your entries and click Finish.
12. On the Identity Sources tab, validate that vclass.local has been added as an identity source.
Q1. What is the Type listed for the vclass.local identity source?
1. vclass.local is listed as Active Directory (Integrated Windows Authentication).

Task 3: View Active Directory Users
1. In the Navigator pane, under Single Sign-on click Users and Groups.
2. In the Users and Groups pane, the Users tab opens.
3. On the Users tab, select vclass.local from the Domain drop-down menu.
4. Locate the Administrator user name.
The Administrator account is used in the next task.

Task 4: Assign Object Permissions to an Active Directory User
Permission is assigned at a vCenter Server level and propagated to children objects. The assigned
permission applies to objects such as data centers, folders, clusters, hosts, virtual machines and other
vCenter Server level objects.
In vSphere Web Client, click the Home icon and select Hosts and Clusters.
1. Right click sa-vcsa-01.vclass.local and click Add Permission.
2. In the sa-vcsa-01.vclass.local - Add Permissions wizard, select Administrator and assign a
role.
a. Under Users and Groups, click Add.
b. On the Select Users/Groups page, select vclass.local from the Domain drop-down menu.
c. Under Users and Groups, click Administrator.
d. Click Add.
e. Verify that vclass.local\Administrator is listed in the Users text field.
f. Click Check names.
g. In Correct usernames, click OK
h. In Select User/Groups, click OK.
i. Under Assigned Role, select Administrator from the Assigned Role drop-down menu.
j. In sa-vcsa-01.vclass.local - Add Permission, click OK.

Task 5: Assign Root-Level Global Permission
Object level permissions are not available for Content Libraries, the direct parent for content
libraries is the global root. To assign a permission on a content library, an Administrator must grant
the permission to the user as a global permission.
1. Click the Home icon and select Administration.
2. In the Navigator pane, navigate to Access Control and select Global Permissions.
3. In the Global Permissions pane, click Manage, and then click the Add permission icon (the green
plus sign)
4. In the Global Permissions Root - Add Permissions wizard, select Content library administrator
(sample) and assign a role.
a. Under Users and Groups, click Add.
b. On the Select Users/Groups page, select vclass.local from the Domain drop-down menu.
c. Under Users and Groups, click Administrator.
d. Click Add.
e. Verify that vclass.local\Administrator is listed in the Users text field.
f. Click Check names.
g. In Correct usernames, click OK.
h. In Select User/Groups, click OK.
i. Under Assigned Role, select Content library administrator (sample) from the Assigned
Role drop-down menu.
j. In sa-vcsa-01.vclass.local - Add Permission, click OK.
k. Verify that VCLASS.LOCAL\Administrator is included in the User/Group list as
Administrator.
5. Log out of vSphere Web Client.
Task 6: Log In with Windows Session Authentication
You now have the option to log in to vSphere Client or vSphere Web Client as
administrator@vclass.local or administrator@vsphere.local to complete the remaining labs.
1. On the vSphere Web Client (SA-VCSA-01) login screen, select the Use Windows session
authentication check box and click Login.
2. You are logged in to vSphere Web Client (SA-VCSA-01) as administrator@vclass.local.
Task 7: Use an Active Directory User to Manage a Virtual Machine
1. In vSphere Web Client, click the Home icon and select VMs and Templates.
2. In the Navigator pane, expand SA-Datacenter.
3. Right-click Photon-ForTemplate and select Template > Convert to Template.
4. Click Yes to verify converting the virtual machine to a template.
5. In the Navigator pane, drag the Photon-ForTemplate template into the Templates folder.
6. Expand the Templates folder.
7. Right-click Photon-ForTemplate and select New VM from This Template.
8. On the Select name and folder page, enter Photon-01 in the Virtual Machine Name text box.
9. Expand the view for sa-vcsa-01.vclass.local > SA-Datacenter, select the Lab VMs folder and
click Next.
10. On the Select a compute resource page, expand SA-Datacenter > Lab Servers.
11. Select the sa-esxi-01.vclass.local host and click Next.
12. On the Select storage page, select Class-Datastore.
13. From the Select virtual disk format drop-down menu, select Thin Provision and click Next.
14. On the Select Clone options page, accept the default settings and click Next.
15. On the Ready to complete page, review the information and click Finish.
16. In the Recent Tasks pane, monitor the progress of the template deployment task and wait for
completion.
17. In the navigator pane, select Photon-01.
18. In the right pane, click the Summary tab.
19. In the Navigation pane, right-click Photon-01, then click Delete from Disk.
20. Click Yes to verify the deletion.
21. Log out of vSphere Web Client and close the Firefox Web browser.
22. In the next lab, you use vSphere Client to perform the tasks.
23. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

-------------------------------------- P2 ----------------------------------------------------------------
(A) Aim: Create a standard switch and a port group.
Objective: In this lab, you perform the following tasks:
1. View the Standard Switch Configuration
2. Create a Standard Switch with a Virtual Machine Port Group
3. Attach Your Virtual Machines to the New Virtual Machine Port Group
4. In this lab, you use vSphere Client to perform the tasks.
Steps:
Task 1: View the Standard Switch Configuration
You view the VMware vSphere® standard switch settings to ensure proper configuration of the default
switch.
1. Open your Firefox web browser, click vSphere Site-A on the favorite bar and select vSphere Client
(SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. vSphere Client opens to the Hosts and Clusters view in the Navigator pane.
4. In the Navigator pane, click the arrows to expand the view.
5. Select sa-esxi-01.vclass.local, click on the Configure tab, and select Virtual switches in the middle
pane.
6. In the Virtual switches pane, select the displayed virtual switch and review the information about
the virtual switch.

Task 2: Create a Standard Switch with a Virtual Machine Port Group
You create a virtual machine port group on a standard switch, which handles network traffic at the
host level in your vSphere environment.
1. In the center pane, click Add Networking
The sa-esxi-01.vclass.local - Add Networking wizard opens.
2. On the Select connection type page, click Virtual Machine Port Group for a Standard Switch
and click Next.
3. On the Select target device page, click New standard switch and click Next.
4. On the Create a Standard Switch page, click the Add adapters icon (the green plus sign).
5. Select vmnic3 and click OK.
6. Review the information for the new active adapter and click Next.
7. On the Connection settings page, enter Production in the Network label text box and click Next.
8. On the Ready to complete page, verify that the information is accurate and click Finish.
9. In the Virtual switches pane, select vSwitch1.
The vSwitch1 standard switch and the Production port group are added to the Virtual switches pane.
You might need to click and move the adjustment slider that divides the Virtual switches pane and
the detail pane to display the newly created standard switch. You can also minimize the Recent
Tasks pane.
10. Repeat task 2 for your second ESXi host sa-esxi-02.vclass.local.

Task 3: Attach Your Virtual Machines to the New Virtual Machine Port Group
You attach the virtual machine to the virtual machine port group so that the virtual machine can
communicate with other networked devices.
1. In vSphere Client, click the Menu icon and select VMs and Templates.
2. In the Navigator pane, click the arrows to expand the view of your Datacenter and folders.
3. In the Navigator pane, select the Win10-01 virtual machine.
When repeating this task, select the Win10-02 virtual machine.
4. Ensure that Win10-01 is powered on.
5. Right-click the virtual machine and select Edit Settings.
6. In Edit Settings, find Network adapter 1.
7. Click the downward arrow next to VM Network, and click Browse.
8. In Select Network, select Production and click OK.
9. Expand Network adapter 1 and verify that the Connect At Power On and Connected check boxes
are selected.
10. Click OK to close the Edit Settings window.
11. Renew the virtual machine’s IP address.
a. From the Summary tab, click Launch Web Console.
b. You are logged in to the virtual machine as vclass\administrator with the password
VMware1!.
c. Right click the Windows icon and select Run.
d. In the Run dialog box, enter cmd and click OK to open a Command Prompt window.
e. At the command prompt, run the ipconfig /release command.
f. Run the ipconfig /renew command.
g. Record the virtual machine’s IP address.
h. Record the virtual machine’s default gateway.
12. At the virtual machine’s command prompt, ping the Production network’s default gateway
172.20.11.10 to verify that the virtual machine is connected to the network.
Your ping should be successful. If it is not successful, ask your instructor for help.
13. Power on the Win10-02 virtual machine, and repeat steps 5 through 11.
14. Close the Command Prompt and Web Console for both the virtual machines.
15. Leave vSphere Client open for the next lab.
16. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

(B) Aim: Configure access to an iSCSI datastore.
Objective: In this lab, you perform the following tasks:
1. Validate an Existing ESXi Host iSCSI Configuration
2. Add a VMkernel Port Group to a Standard Switch
3. Configure the iSCSI Software Adapter
4. Connect the iSCSI Software Adapters to Storage
In this lab, you use vSphere Client to perform the tasks.
Steps:
Task 1: Validate an Existing ESXi Host iSCSI Configuration
You use VMkernel interfaces to provide network connectivity for your hosts and to handle other types
of traffic, such as VMware vSphere® vMotion® traffic, storage traffic, and VMware vSphere® Fault
Tolerance traffic. In this task, you validate an existing VMkernel and iSCSI software adapter
configuration on your first host.
1. In vSphere Client, click the Menu icon and select Hosts and Clusters.
2. In the Navigator pane, select sa-esxi-01.vclass.local.
3. In the right pane, the Configure tab is open.
4. In the center pane, select Storage > Storage Adapters.
5. In the Storage Adapters pane, validate iSCSI Software Adapter.
a. Scroll and select the existing iSCSI software adapter.
b. Verify that Online is shown in the Status column.
6. In the Storage Adapters pane, open the Properties tab.
a. Record the storage adapter properties.
Under Adapter Status
• Status
Under General
• Name
• SCSI Name
 Under Authentication
• Method
7. Open the Devices tab and verify that MSFT iSCSI Disk devices are present.
8. Open the Dynamic Discovery tab.
• Record the iSCSI Server IP address
9. Open the Static Discovery tab.
• Record the second iSCSI Server IP address and port
10. Open the Network Port Binding tab.
a. In the Port Group column, click Management Network (vSwitch0).
b. Click View Details.
The Details for vmk0 page opens.
The information that you recorded in step 8 and step 9 can also be seen in the Details for
vmk0 page.
c. Click Close.

Task 2: Add a VMkernel Port Group to a Standard Switch
In this task you configure a VMkernel Port Group on your second host.
1. In the Navigator pane, select sa-esxi-02.vclass.local.
2. On the Configure tab, select Networking > VMkernel adapters.
3. Click the Add Networking icon.
a. The Add Networking wizard appears.
4. On the Select connection type page, verify that VMkernel Network Adapter is selected and click
Next.
5. On the Select target device page, click Select an existing standard switch.
6. Click Browse and select vSwitch0.
7. Click OK.
8. Click Next.
9. On the Port properties page, configure the VMkernel network settings.
a. Enter IP Storage in the Network label text box and click Next.
b. On the IPv4 settings page, click Use static IPv4 settings.
c. In the IPv4 address text box, enter 172.20.10.62.
d. Enter 255.255.255.0 in the Subnet mask text box.
e. Verify that the default gateway is set to 172.20.10.10.
f. Click Next.
10. On the Ready to complete page, click Finish

Task 3: Configure the iSCSI Software Adapter
You configure the iSCSI software adapter on your second ESXi hosts and verify its iSCSI name.
1. In the Navigator pane, select ESXi host sa-esxi-02.vclass.local.
2. On the Configure tab, navigate to Storage and select Storage Adapters.
3. Click the Add Software Adapter icon (the plus sign).
The Add Software Adapter wizard opens.
4. Add software iSCSI adapter is selected.
5. Click OK.
6. In the Storage Adapters list, scroll down and select the newly created iSCSI software adapter.
7. In the Adapter pane, click the Properties tab.
8. Verify that the adapter status is Enabled.
9. Click Edit next to General.
10. Verify that the name shown in the iSCSI Name text box matches iqn.1998-
01.com.vmware:sa-esxi-02-########.
# represents characters that might change.
11. Click OK.
Task 4: Connect the iSCSI Software Adapters to Storage
You connect the iSCSI adapters on the ESXi hosts to directly connect to a remote iSCSI target onthe
IP network.
1. In the Storage Adapter pane, click the Network Port Binding tab.
2. Click the Add icon (the plus sign).
3. Select the IP Storage check box and click OK.
4. In the Storage Adapter pane, click Dynamic Discovery, and click Add.
5. On the Add Send Target Server page, enter 172.20.10.10 for the iSCSI server name in the
iSCSI Server text box and click OK.
6. Monitor the Recent Tasks pane and wait for the task to complete.
7. Click the Rescan Storage Adapters icon.
8. When the rescan storage message appears, click OK and wait for the task to complete.
9. In the Storage Adapter pane, click the Devices tab.
10. Verify that five LUNs appear and record the values.
• LUN number
• Capacity
• Operational state
• Hardware Acceleration
The LUNs are hosted by an iSCSI provider and are used to create datastores in later labs.
11. Compare the results for both the hosts.
12. Leave vSphere Client open for the next lab.
13. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

-------------------------------------------------------------- P3 ----------------------------------------------------
(A) Aim: Create and manage VMFS datastores
Objective: In this lab, you perform the following tasks:
1. Create VMFS Datastores for the ESXi host
2. Expand a VMFS Datastore to Consume Unused Space on a LUN
3. Remove a VMFS Datastores
4. Extend a VMFS Datastores
5. Create a Second Shared VMFS Datastores Using iSCSI
Steps:
Task 1: Create VMFS Datastores for the ESXi Host
You set up VMFS datastores on iSCSI-based storage devices to be used as repositories by virtual
machines.
1. If vSphere Client is not active, open your Firefox web browser, click vSphere Site-A Client in the
favorites bar, and select vSphere Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. In vSphere Client, click the Menu icon and select Hosts and Clusters.
4. Right-click SA-Datacenter and select Storage > New Datastore to start the New Datastore wizard.
5. On the Type page, verify that VMFS is selected and click Next.
6. On the Name and device selection page, enter VMFS-2 in the Datastore name text box.
7. From the Select a host to view its accessible disks/LUNs drop-down menu, select your first host
sa-esxi-01.vclass.local.
A LUN list appears.
8. In the LUN list, select LUN 2 and click Next.
9. On the VMFS version page, accept VMFS 6 and click Next.
10. On the Partition configuration page, reduce the LUN size.
a. Move the Datastore Size slider to reduce the LUN size by 3 GB.
b. Click Next.
11. On the Ready to complete page, review the information and click Finish.
12. Right-click SA-Datacenter in the inventory and select Storage > New Datastore.
13. On the Type page, verify that VMFS is selected and click Next.
14. On the Name and device selection page, enter VMFS-3 in the Datastore name text box.
15. From the Select a host to view its accessible disks/LUNs drop-down menu, select sa-esxi02.vclass.local.
A LUN list appears.
16. From the LUN list, select LUN 3 and click Next.
17. On the VMFS version page, accept VMFS 6 and click Next.
18. On the Partition configuration page, accept the default (full capacity) and click Next.
19. On the Ready to complete page, review the information and click Finish.
20. Monitor the progress in the Recent Tasks pane until the task is completed.
21. In the Navigator pane, click the Storage icon.
22. Expand SA-Datacenter, verify that the VMFS-2 and VMFS-3 datastores are listed in the datastore
inventory.
23. In the datastore inventory, click the VMFS-2 datastore.
24. Click the Summary tab and record the value for storage capacity.

Task 2: Expand a VMFS Datastore to Consume Unused Space on a LUN
You dynamically increase the capacity of a VMFS datastore when more space is required by virtual
machines.
1. In the Navigator pane, right-click the VMFS-2 datastore and select Increase Datastore Capacity
to open the Increase Datastore Capacity wizard.
2. On the Select Device page, select LUN 2.
3. Yes should appear in the Expandable column of LUN 2.
4. Click Next.
5. On the Specify Configuration page, accept Use “Free Space 3.00 GB” to expand the datastore
from the Partition configuration drop-down menu and click Next.
6. On the Ready to Complete page, review the information and click Finish.
7. When the task is completed, select the VMFS-2 datastore in the Navigator pane.
8. On the Summary tab, verify that the datastore size is increased to the maximum capacity, minus
the space required for system overhead.
The new capacity for the VMFS-2 datastore should be 9.75 GB

Task 3: Remove a VMFS Datastore
You can delete any type of VMFS datastore, including the copies that you mounted without
resignaturing. When you delete a datastore, it is destroyed and removed from all hosts.
1. In the Navigator pane, right-click the VMFS-3 datastore and select Delete Datastore.
2. When the Confirm Delete Datastore message appears, click Yes and wait for the task to be complete.
3. In Recent Tasks, verify that the remove datastore task has completed.
4. Verify that the VMFS-3 datastore has been removed from the Navigator pane.

Task 4: Extend a VMFS Datastore
You extend the capacity of a VMFS datastore when extra storage space is needed. You use a second
LUN to extend the size of a datastore based on the first LUN.
1. In Navigator pane, click the VMFS-2 datastore.
2. Click the Configure tab.
3. Select General from the center pane and click Increase.
The Increase Datastore Capacity wizard starts.
4. On the Select Device page, select LUN 3 and click Next.
5. On the Specify Configuration page, select Use all available partitions from the Partition
Configuration drop-down menu and click Next.
The following message is expected: There is no extent of the datastore on this device. Selecting any
configuration option will add a new extent to the datastore.
6. On the Ready to Complete page, review the information and click Finish.
7. When the task completes, refresh the page and select Device Backing in the middle pane.
8. Verify that two extent device names appear in the Extent Name pane.
The Extent Name pane should show both of your assigned devices. You might need to adjust the
size of the Extent Name pane to view all the extent names.
The screenshot shows the two extents listed in the Extent Name pane and the slider to adjust the
size of the pane.
9. Click the Summary tab.
10. Record the new value for Total Capacity in the Summary tab.
The value should be different from the value seen in task 2, step 7.
11. On the Summary tab, click the Hosts tab in right pane.
The two hosts are connected, indicating that this new datastore is shared between your two ESXi
hosts.
12. Right-click your VMFS-2 datastore in the Navigator pane and select Rename.
13. In the Enter the new name text box, enter Shared-VMFS.
14. Click OK.

Task 5: Create a Second Shared VMFS Datastore Using iSCSI
You use an iSCSI shared LUN to create a VMFS6 file system.
1. In vSphere Client, click the Menu icon and select Hosts and Clusters.
2. Right-click SA-Datacenter and select Storage > New Datastore.
The New Datastore wizard starts.
3. On the Type page, verify that VMFS is selected and click Next.
4. On the Name and device selection page, in the Datastore name text box enter iSCSIDatastore.
5. From the Select a host to view its accessible disks/LUNs drop-down menu, select sa-esxi01.vclass.local.
A LUN list appears.
6. From the newly displayed LUN list, select LUN 5 named MSFT iSCSI Disk (Capacity 139.85 GB)
and click Next.
7. On the VMFS version page, accept VMFS 6 and click Next.
8. On the Partition configuration page, accept Use all available partitions and click Next.
9. On the Ready to complete page, review the information and click Finish.
10. Click the Storage icon in the navigator pane.
11. Verify that iSCSI-Datastore is listed in the Storage view.
12. On the Configure tab, select Connectivity and Multipathing to verify that both hosts can see the
datastore.
13. Leave vSphere Client open for the next lab.
14. Inform your instructor that you have completed this lab. If prompted, continue to the next lab

(B) Aim: Configure access to an NFS datastore.
Objective: In this lab, you perform the following tasks:
1. Configure access to an NFS datastore
2. View NFS Storage information
Steps:
Task 1: Configure Access to NFS Datastores
You mount an NFS share to your ESXi hosts and use it as a datastore.
1. If vSphere Client is not active, open your Firefox Web browser, click vSphere Site-A on the favorite
bar, and select vSphere Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. In vSphere Client, click the Menu icon and select Storage.
4. Right-click SA-Datacenter and select Storage > New Datastore.
The New Datastore wizard starts.
5. On the Type page, select NFS and click Next.
6. On the Select NFS version page, select NFS 4.1 and click Next.
7. On the Name and configuration page, enter NFS-Datastore in the Datastore name text box.
8. Enter /NFS-Data as the folder name in the Folder text box.
9. Enter 172.20.10.10 as the NFS server name in the Server text box.
10. Click the Add server icon (the green plus sign).
11. Validate that 172.20.10.10 is added to the Servers to be added box and click Next.
12. On the Configure Kerberos authentication page, accept the default, and click Next.
13. On the Host accessibility page, select both the ESXi hosts and click Next.
14. On the Ready to complete page, verify the NFS settings and click Finish.
15. Verify that your NFS datastore is listed in the Navigator pane.
Task 2: View NFS Storage Information
You view information about your NFS storage and the contents in the NFS datastore.
1. Select your NFS-Datastore datastore in the Navigator pane.
2. Click the Summary tab.
3. View the content pane and record the information about the datastore.
a) Datastore type
b) Capacity of the datastore
c) Free space of the datastore
d) Used space of the datastore
4. Leave vSphere Client open for the next lab.
5. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

(C)Aim: Deploy a new virtual machine from a template and clone a virtual machine.
Objective: In this lab, you perform the following tasks:
1. Create a Virtual Machine Template
2. Create Customization Specifications
3. Deploy a VM from a Template
Steps:
Task 1: Create a Virtual Machine Template
You create a template to securely preserve a virtual machine configuration and easily deploy new virtual
machines from the template.
1. If vSphere Client is not active, open your Firefox web browser, click vSphere Site-A on the favorite
bar, and select vSphere Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. In vSphere Client, click the Menu icon and select VMs and Templates.
4. Right-click the Win10-01virtual machine and select Power > Shut Down Guest OS.
5. Click Yes to verify shut down and wait for the virtual machine to power off completely.
6. Right-click the Win10-01 virtual machine and select Template > Convert to Template.
7. Click Yes to verify the conversion.
8. Right-click the Win10-01 virtual machine template and select Move To Folder.
9. Select Templates in the Move to Folder pane and click OK.
10. Expand the Templates folder.
11. Right-click the Win10-01 virtual machine template and select Rename.
12. Enter Win10-Template and click OK.
Task 2: Create Customization Specifications
You save the guest operating system settings in a customization specification file, which is applied when
you clone virtual machines or deploy virtual machines from templates.
1. In vSphere Client, click the Menu icon and select Policies and Profiles.
2. Under Policies and Profiles, click VM Customization Specification and click the Create a new
specification icon.
The New VM Guest Customization Spec wizard opens.
3. On the Name and target OS page, enter Win10-CustomSpec in the Customization Spec Name text
box.
4. Verify that sa-vcsa-01.vclass.local shows next to vCenter Server.
5. Under Guest OS, verify that Windows is selected as the Target guest OS.
6. Verify that Generate a new security identity (SID) is selected.
7. Click Next.
8. On the Registration Information page, enter VMware Student in the Owner name text box, and
enter VMware in the Owner organization text box
9. Click Next.
10. On the Computer Name page, select Use the virtual machine name and click Next.
11. On the Enter Windows License page, leave the product key text box blank, leave other settings at
their defaults and click Next.
12. On the Administrator Password page, enter the password VMware1! and verify it.
13. Click Next.
14. On the Time Zone page, select (GMT-08:00) Pacific Time (US & Canada) from the Time Zone
drop-down menu and click Next.
15. On the Commands to Run Once page, click Next.
16. On the Network page, verify that Use standard network settings for the guest operating system,
including enabling DHCP on all network interfaces is selected and click Next.
17. On the Workgroup or Domain page, verify that Workgroup is clicked and that the text box shows
WORKGROUP.
18. Click Next.
19. On the Ready to complete page, review the information and click Finish.
20. In the Customization Specification Manager pane, verify that Win10-CustomSpec is listed.
Task 3: Deploy a Virtual Machine from a Template
You use templates to rapidly deploy and provision new virtual machines and easily customize the guest
operating systems.
1. Click the Menu icon and select VMs and Templates.
2. Right-click Win10-Template and select New VM from this Template.
The Deploy From Template wizard opens.
3. On the Select a name and folder page, enter Win10-03 in the Virtual machine name text box.
4. In the Select a location for the virtual machine page, expand SA-Datacenter and select the Lab
VMs folder.
5. Click Next.
6. On the Select a compute resource page, expand SA-Datacenter > Lab Servers and select saesxi01.vclass.local.
The Compatibility pane displays the Compatibility checks succeeded message.
7. Click Next.
8. On the Select storage page, select iSCSI-Datastore from the Storage Compatibility: Compatible
list.
The Compatibility pane displays the Compatibility checks succeeded message.
9. From the Select virtual disk format drop-down list, select Thin Provision.
10. Click Next.
11. On the Select clone options page, select the Customize the operating system and the Power on
virtual machine after creation check boxes and click Next.
12. On the Customize guest OS page, select Win10-CustomSpec and click Next.
13. On the Ready to complete page, review the information and click Finish.
14. Repeat steps 2 through 13 to create another virtual machine on your second host named Win10-04.
15. In the Recent Tasks pane, monitor the progress of the two template deployment tasks and wait for
their completion.
16. Open a console for each of the newly created virtual machines.
a. In the Navigator pane of vSphere Client, right-click the Win10-03 virtual machine and
select Open Remote Console
An alternative to using Remote Console is the Web Console launched from the virtual
machine Summary tab.
b. In the Invalid Security Certificate screen, select the Always trust this host with this
certificate check box.
c. Click Connect Anyway.
When the virtual machine console opens, you might see the Windows setup process continuing. It
automatically reboots a few times to complete the process.
17. You are logged in as vclass\administrator with the password VMware1!.
18. Verify that both IOMETER and CPUBUSY are on the desktop.
19. Verify that VMware Tools is installed by navigating to the Windows system tray at the lower right
corner to show hidden icons and double-click the VMware Tools icon.
20. Repeat steps 16 through 18 for the Win10-04 virtual machine.
21. Close the virtual machine console for both virtual machines.
Since Remote Console is used, close Remote Console on the task bar and close the empty Firefox
tab for each virtual machine.
22. Leave vSphere Client open for the next lab.
23. Inform your instructor that you have completed this lab. If prompted, continue to the next lab

------------------------- P4 --------------------------------------------------
(A) Aim: Create a content library to clone and deploy virtual machines.
Objective: In this lab, you perform the following tasks:
1. Create a Conent Library
2. Clone a VM Tempate to a Template in a content library
3. Deploy a VM from a VM Template in the content library
4. Delete a content library
Steps:
Task 1: Create a Content Library
You create a content library in vSphere Client and populate it with templates, which you can use to
deploy virtual machines or vApps in your virtual environment.
1. If vSphere Client is not active, open your Firefox web browser, click vSphere Site-A on the favorite
bar, and select vSphere Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. In vSphere Client, click the Menu icon and select Content Libraries.
4. In the center pane, click the Create a new content library icon (plus sign) under Content
Libraries.
5. On the Name and location page, enter VM_Library in the Name text box and click Next.
6. In the Configure content library page, verify that Local content library is selected.
7. Select the Publish externally check box, and click Next.
8. In the Add storage page, select iSCSI-Datastore, and click Next.
9. On the Ready to complete page, review the information and click Finish.
10. Wait for this task to finish before you go to the next task.
Task 2: Clone a VM Template to a Template in a Content Library
You clone virtual machines or VM templates from the vCenter Server inventory to templates in the
content library and use them later to provision virtual machines on a cluster or a host. You can also
clone a virtual machine or VM template to update an existing template in the library.
1. In vSphere Client, click the Menu icon and select VMs and Templates.
2. Expand the view of the data center and all folders.
3. Right-click Photon-ForTemplate and select Clone to Template in Library.
4. For Clone as, verify that New template is selected.
5. Under the Name column, select VM_Library.
6. Enter Photon-LibTemplate in the template name text box.
7. Click OK and wait for the task to finish before you go to the next task.
This process takes about 10 minutes.
Task 3: Deploy a Virtual Machine from a VM Template in the Content Library
You use a virtual machine template from a content library to deploy a virtual machine to a host or a
cluster in your vSphere inventory.
1. In vSphere Client, click the Menu icon and select Content Libraries.
2. In Content Libraries, select VM_Library.
3. Click the Templates tab.
4. Right-click Photon-LibTemplate and select New VM from This Template.
5. On the Select name and folder page, enter Photon-FromLib in the Virtual Machine Name text
box.
6. In Select a location for the virtual machine pane, expand sa-vcsa-01.vclass.local, select
SADatacenter and click Next.
7. On the Select a compute resource page, expand SA-Datacenter and select the sa-esxi02.vclass.local host.
8. Click Next.
9. On the Review details page, review the information and click Next.
10. On the Select storage page, select Class-Datastore.
11. From the Select virtual disk format drop-down menu, select Thin Provision and click Next.
12. On the Select Networks page, select Production from the Destination Network drop-down menu
and click Next.
13. On the Ready to complete page, review the information and click Finish.
14. In the Recent Tasks pane, monitor the progress of the template deployment task and wait for
completion.
15. In vSphere Client, click the Menu icon and select VMs and Templates.
16. In the navigator pane, select Photon-FromLib.
17. Right-click Photon-FromLib and select Power > Power On.
18. Open a console for the Photon-FromLib virtual machine.
a. On the Summary tab, click Launch Web Console.
19. Verify that the Photon-FromLib virtual machine is running.
20. Close the Web Console for the Photon-FromLib virtual machine.
vSphere Client returns to VMs and Templates.
Task 4: Delete a Content Library
You delete a content library that is no longer required.
1. In vSphere Client, click the Menu icon and select Content Libraries.
2. In Content Libraries, right-click the VM_Library content library and select Delete.
3. In the Delete Content Library confirmation dialog box, click OK to verify the deletion.
4. Leave vSphere Client open for the next lab.
5. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

(B) Aim: Modify a virtual machine’s hardware and add a raw LUN to a virtual machine.
Objective: In this lab, you perform the following tasks:
1. Clone a Powered-On VM
2. Increase the Size of a VMDK File
3. Adjust Memory Allocation on a VM
4. Rename a VM in the vCenter Server Appliance Inventory
5. Add and Remove a Raw LUN on a VM
Steps:
Task 1: Clone a Powered-On Virtual Machine
You clone a virtual machine to create a new virtual machine with the same virtual hardware,installed
software, configuration, and other properties. The original virtual machine can be powered on, off, or
suspended.
1. If vSphere Client is not active, open your Firefox web browser, click vSphere Site-A on the favorite
bar, and select vSphere Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. In vSphere Client, click the Menu icon, and select VMs and Templates.
4. In the Navigator pane, expand the SA-Datacenter and the Lab VMs folder.
5. Ensure the Win10-02 virtual machine is powered on.
6. Right-click the Win10-02 virtual machine and select Clone > Clone to Virtual Machine.
The Clone Existing Virtual Machine wizard starts.
7. On the Select a name and folder page, enter Win10-Clone in the Virtual machine text box.
8. Expand SA-Datacenter and select Lab VMs from the Select a location for the virtual machine
pane and click Next.
9. On the select a compute resource page, expand Lab Servers and select sa-esxi-02.vclass.local from
the Select a compute resource pane and click Next.
10. On the Select storage page, select iSCSI-Datastore.
11. Select Thin Provision from the Select virtual disk format drop-down menu and click Next.
12. On the Select clone options page, select the Customize the operating system and the Power on
virtual machine after creation check boxes.
13. Click Next.
14. On the Customize guest OS page, select Win10-CustomSpec and click Next.
15. On the Ready to complete page, review the information and click Finish.
16. Monitor the progress of the task in the Recent Tasks pane.
This task takes 10 minutes to complete.
17. Open a console for the Win10-Clone virtual machine.
a. In the Navigator pane of vSphere Client, right-click the Win10-Clone virtual machine and
select Open Remote Console.
When the virtual machine console opens, you might see the Windows setup process
continuing. It automatically reboots a few times to complete the process.
b. You are logged in as vclass\administrator with the password VMware1!.
c. Verify that VMware Tools is installed by navigating to the Windows system tray at the
lower-right corner to show hidden icons and double-click the VMware Tools icon.
18. Close the virtual machine console.

Task 2: Increase the Size of a VMDK File
You increase the size of the virtual machine disk (VMDK) and configure the guest operating system to
detect the additional space.
1. Right-click your Win10-Clone virtual machine in the Navigator pane and select Edit Settings.
2. On the Virtual Hardware tab, record the size (GB) of Hard Disk 1. __________
3. In the Hard disk 1 text box, increase the disk size by 2 GB and click OK.
4. On the Win10-Clone Summary tab, select Launch Web Console.
5. Configure the Win10-Clone virtual machine’s guest operating system to detect and extend the
increased disk space.
a. Right-click Start, then click on Disk Management.
b. In the lower-right pane, verify that the 2 GB unallocated disk space is discovered.
If the 2.00 GB of unallocated space has not been discovered, click the Action menu, and select Rescan
Disks.
c. Right-click the C: drive and select Extend Volume.
The Extend Volume wizard starts.
d. Click Next.
e. On the Select Disks page, verify that Disk 0 is selected in the Selected pane and click Next.
f. On the Completing the Extend Volume Wizard page, review the information and click
Finish.
g.
6. In the Disk Management window, verify that the local C: drive (Disk 0) is extended.
7. Record the value for the total size of the C: drive. __________
8. Compare the value with the value that you recorded in step 2.
9. Close the Disk Management window.
10. Close the virtual machine console.

Task 3: Adjust Memory Allocation on a Virtual Machine
You add, change, or configure virtual machine memory resources or options to enhance virtual machine
performance.
1. Right-click the Win10-Clone virtual machine and select Power > Shut Down Guest OS from the
Navigator pane.
2. Click Yes to verify the shutdown.
3. On the Win10-Clone Summary tab expand the view of the VM Hardware pane and record the
4. amount (GB) of active memory. __________
5. Right-click the Win10-Clone virtual machine in the Navigator pane, and select Edit Settings.
6. Enter 2500 in the Memory text box and verify that MB is selected from the drop-down menu.
7. Click OK.
8. Verify that the memory is increased on the virtual machine’s Summary tab.

Task 4: Rename a Virtual Machine in the vCenter Server Appliance Inventory
You rename an existing virtual machine in the vCenter Server Appliance inventory.
1. In the Navigator pane, right-click the Win10-Clone virtual machine and select Rename.
2. In the Enter the new name text box, enter Win10-05.
3. Click OK.
4. In the Navigator pane, select Win10-05 virtual machine and click the Datastores tab.
5. Right-click iSCSI-Datastore and select Browse Files.

Task 5: Add and Remove a Raw LUN on a Virtual Machine
You use raw device mapping (RDM) to enable a virtual machine to access a LUN directly.
1. Click the VMs and Templates icon.
2. Right-click the Win10-05 virtual machine and select Edit Settings.
3. Select RDM Disk from the New device drop-down menu.
4. In the Select Target LUN dialog box, select LUN 4 and click OK.
5. Click the arrow next to New Hard disk to expand the view.
6. In the Location drop-down menu, verify that Store with the virtual machine is selected.
7. Select Virtual from the Compatibility Mode drop-down menu, and click OK.
8. Verify that the guest operating system can see the new disk.
a. In the Navigator pane, right-click the Win10-05 virtual machine and select Power > Power
On.
b. Right-click the Win10-05 virtual machine and select Open Remote Console.
c. You are logged in as vclass\administrator with the password VMware1!.
d. Right-click Start, then click on Disk Management.
e. When the Initialize Disk wizard starts, click Cancel.
f. Verify that Disk 1 is listed.
g. Close the Disk Management window.
9. Close the virtual machine console and the Firefox browser tab.
10. In vSphere Client, remove the RDM hard disk from the Win10-05 virtual machine.
a. Right-click the Win10-05 virtual machine and select Power > Shut Down Guest OS.
b. Click Yes to verify the shut down and wait for the virtual machine to power off.
c. Right-click the Win10-05 virtual machine and click Edit Settings.
d. Point to Hard disk 2 in the edit setting dialog box.
e. Click the x icon that appears at the right side of the row for Hard disk 2.
f. Select the Delete files from datastore check box and click OK.
11. Leave vSphere Client open for the next lab.
12. Inform your instructor that you have completed this lab. If prompted, continue to the next lab

------------------------------------------------- P5 ----------------------------------------------------------------------------------------------------
Aim: Use vSphere vMotion and vSphere Storage vMotion to migrate virtual machines.
Objective: In this lab, you perform the following tasks:
1. Migrate Virtual Machine Files from Local Storage to Shared Storage
2. Create a Virtual Switch and a VMkernel Port Group for vSphere vMotion Migration
3. Prepare Virtual Machines to Demonstrate vSphere vMotion Migration
4. Perform vSphere vMotion Migrations of Virtual Machines
5. Perform Compute Resource and Storage Migrations
In this lab, you use vSphere Client to perform the tasks.
Steps:
Task 1: Migrate Virtual Machine Files from Local Storage to Shared Storage
With VMware vSphere® Storage vMotion®, you can migrate a virtual machine’s disk files from one
datastore to another while the virtual machine is running.
1. If vSphere Client is not active, open your Firefox web browser, click vSphere Site-A on the favorite
bar, and select vSphere Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. Click the Menu icon and select VMs and Templates.
4. Verify that the Win10-02 virtual machine is selected and powered on.
5. On the Summary tab, in the Related Objects pane, record the name of the storage on which the
Win10-02 virtual machine resides
6. Right-click the Win10-02 virtual machine and select Migrate. The Migrate wizard opens.
7. Select Change storage only on the Select a migration type page and click Next.
8. On the Select Storage page, select iSCSI-Datastore as the destination storage for the virtual machine
files. In the Compatibility pane, the Compatibility checks succeeded message appears.
9. Click Next.
10. On the Ready to complete page, review the information and click Finish.
11. Monitor the Recent Tasks pane and wait for the virtual machine files relocation process to complete.
This task takes several minutes to complete.
12. Repeat step 5 and step 6 to verify that the Win10-02 virtual machine is on the new datastore, which
is iSCSI-Datastore.

Task 2: Create a Virtual Switch and a VMkernel Port Group for vSphere vMotion
Migration You create a VMkernel port group virtual switch to move virtual machines from one host
to another while maintaining continuous service availability.
1. Click the Menu icon and select Hosts and Clusters.
2. In the Navigator pane, expand SA-Datacenter > Lab Servers and select the host sa-esxi01.vclass.local.
3. Click the Configure tab.
4. In the middle pane, navigate to Networking and select Virtual switches.
5. Click the Add Networking icon to open the Add Networking wizard.
6. Accept VMkernel Network Adapter in the Select connection type page and click Next
7. Select New standard switch in the Select target device page and click Next.
8. Click the green + sign in the Create a Standard Switch page to add a physical adapter to the switch.
9. Select vmnic2 as the vmnic for the vSphere vMotion network and click OK.
10. Review the information shown and click Next.
11. On the Port properties page for connection settings, enter vMotion in the Network label text box
12. Select the vMotion check box, and click Next.
13. On the IPv4 settings page, configure the IP address.
a. Select Use static IPv4 settings.
b. Enter 172.20.12.51 in the IPv4 address text box for the sa-esxi-01.vclass.local host.
c. Enter 255.255.255.0 in the Subnet mask text box for the vMotion VMkernel port IPv4.
d. Click Next.
14. On the Ready to complete page, review the information and click Finish.
15. In the Virtual Switches pane, verify that the new virtual switch for vSphere vMotion migration is
listed.
16. Repeat steps 2-15 for sa-esxi-02.vclass.local, using 172.20.12.52 for the vMotion VMkernel port
IPv4 address in step 13 b. All other steps remain same.

Task 3: Prepare Virtual Machines to Demonstrate vSphere vMotion Migration
You prepare virtual machines to demonstrate live migration between hosts using vMotion.
1. In the Navigator pane, expand the view of the inventory.
2. Right-click the Win10-03 virtual machine and select Edit Settings.
3. On the Virtual Hardware tab, select Client Device from the CD/DVD drive 1 drop-down menu.
4. Click the arrow next to Network adapter 1 to expand the view.
5. Verify that Production is selected from the drop-down menu.
6. Verify that the Connect At Power On check box is selected for Network adapter 1.
7. Click OK. 8. Repeat steps 2 through 7 for the Win10-04 virtual machine.
8. Verify that the Win10-03 virtual machine is powered on.
9. Right-click the Win10-03 virtual machine and select Open Remote Console.
10. You are logged in as vclass\administrator with the password VMware1!
11. Click the Search Windows icon in Windows Task bar and enter cmd to open a Command Prompt
window.
12. When the Command Prompt window opens, enter the ipconfig command and record the virtual
machine’s default gateway IP address.
13. Enter ping -t default_gateway IP address on the command line to start a continuous ping.

Task 4: Perform vSphere vMotion Migrations of Virtual Machines
You perform live migration of virtual machines residing on a shared datastore that is accessible to both
the source and the target ESXi hosts.
1. Leave the virtual machine console open and return to vSphere Client.
2. Migrate the Win10-03 virtual machine from host sa-esxi-01.vclass.local to host saesxi02.vclass.local.
a. In the Navigator pane, right-click the Win10-03 virtual machine and select Migrate.
b. On the Select a migration type page, accept Change compute resource only and click Next.
c. On the Select a compute resource page, select sa-esxi-02.vclass.local. sa-esxi02.vclass.local is the destination host to which you migrate the Win10-03 virtual machine.
The migration requirements are validated. If the validation does not succeed, you receive
warning or error messages. You cannot continue with the migration until the errors are
resolved.
d. Click Next
e. On the Select networks page, ensure that Production is selected from the Destination
Network drop-down menu and click Next.
f. Leave Schedule vMotion with high priority (recommended) selected on the Select vMotion
priority page and click Next.
g. On the Ready to complete page, review the information and click Finish
3. Return to the Win10-03 virtual machine console and monitor that no pings are dropped during the
migration.
a. Monitor the console for 1 to 2 minutes. If the Win10-03 virtual machine console is
disconnected, reopen the console.
4. Press Ctrl+C to stop the ping.
5. Close the Command Prompt window.
6. Close the Win10-03 virtual machine console.
7. Verify that the Win10-04 virtual machine is powered on.
8. In the Navigator pane, select Win10-04.
9. On the Summary tab, verify that Win10-04 is on the sa-esxi-02.vclass.local host.
10. Migrate the Win10-04 virtual machine from host sa-esxi-02.vclass.local to host saesxi01.vclass.local.
a. In the Navigator pane, drag the Win10-04 virtual machine from sa-esxi-02.vclass.local to
sa-esxi-01.vclass.local. The Migrate wizard opens.
b. On the Select a migration type page, select Change compute resource only and click Next.
c. On the Select a compute resource page, select sa-esxi-01.vclass.local and click Next.
d. On the Select networks page, verify that Production is selected from the Destination
Network drop-down menu and click Next.
e. On the Select vMotion priority page, leave Schedule vMotion with high priority
(recommended) selected and click Next.
f. On the Ready to complete page, review the information and click Finish.
11. When the migration tasks are completed, view the Navigator pane to verify that Win10-04 is under
sa-esxi-01.vclass.local and Win10-03 is under sa-esxi-02.vclass.local.
Task 5: Perform Compute Resource and Storage Migrations
You can migrate virtual machines not only to a different host but also to a different datastore across
storage accessibility boundaries.
1. In the Navigator pane, right-click the Photon-FromLib virtual machine and select Migrate.
2. On the Select a migration type page, click Change both compute resource and storage and click
Next.
3. On the Select compute resource page, expand SA-Datacenter > Lab Servers and select saesxi01.vclass.local.
a. NOTE
b. If the Compatibility alarm – No guest heartbeats are being received message appears, ignore
it. This message does not affect a successful migration.
4. Click Next.
5. On the Select storage page, select iSCSI-Datastore and click Next.
6. On the Select network page, verify that Production is selected from the Destination Network dropdown menu and click Next.
7. On the Select vMotion priority page, leave Schedule vMotion with high priority (recommended)
selected and click Next.
8. On the Ready to complete page, review the information and click Finish.
9. In the Recent Tasks pane, monitor the progress of the virtual machine migration
10. 10. When the migration task is completed, view the Navigator pane to verify that the Photon-From Lib
virtual machine is listed under your sa-esxi-01.vclass.local ESXi host.
11. Right-click Photon-From Lib and select Power > Shut Down Guest OS.
NOTE
If your Shut Down Guest OS option is dimmed, refresh the vSphere Client page and try again.
12. Click Yes to verify the shut down.
13. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

---------------------------------- P6 _----------------------------------------------------
Aim: Perform virtual machine management tasks
Objective: In this lab, you perform the following tasks:
1. Unregister a Virtual Machine from the vCenter Server Appliance Inventory
2. Register a Virtual Machine in the vCenter Server Appliance Inventory
3. Unregister and Delete Virtual Machines from the Datastore
4. Take Snapshots of a Virtual Machine
5. Add Files and Take Another Snapshot of a Virtual Machine
6. Revert the Virtual Machine to a Snapshot
7. Delete an Individual Snapshot
8. Delete All Snapshots In this lab, you use vSphere Client to perform the tasks.
Steps:
Task 1: Unregister a Virtual Machine from the vCenter Server Appliance Inventory
You unregister a virtual machine from the vCenter Server Appliance inventory. Unregistering does not
delete the virtual machine from the datastore.
1. If vSphere Client is not active, open your Firefox web browser, click vSphere Site-A on the favorite
bar, and select vSphere Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. Click the Menu icon and select VMs and Templates.
4. Select theWin10-05 virtual machine and click the Datastores tab.
5. Record the VMFS datastore name where the Win10-05 virtual machine resides.
6. Verify that the Win10-05 virtual machine is powered off.
7. Right-click Win10-05 and select Remove from Inventory.
a. CAUTION
b. Do not select Delete from Disk. This operation is not recoverable in your lab environment.
8. Click Yes to verify the removal.
9. Verify that the Win10-05 virtual machine no longer appears in the Navigator.
10. If needed, click the Refresh icon for vSphere Client.
11. In the Navigator pane, click the Storage icon and expand the view.
12. Click the datastore name that you recorded in step 5.
13. In the right pane, verify that the Files tab is open.
14. View the folders in the middle pane.
Q1. Does a folder named Win10-05 exist?
No, a folder named Win10-05 does not exist. When the Win10-05 virtual machine was first
created, the virtual machine and its folder were named after the original virtual machine,
Win10- Clone. When the virtual machine was renamed from Win10-Clone to Win10-05, the
folder was not renamed.
15. In the middle pane, select the Win10-Clone folder.
16. In the right pane, view the Win10-Clone virtual machine files
17. Task 2: Register a Virtual Machine in the vCenter Server Appliance Inventory
If you removed a virtual machine from the vCenter Server Appliance inventory but did not remove its
folder from the managed host’s datastore, you can return the virtual machine back to the inventory by
registering the virtual machine’s .vmx file with vCenter Server Appliance.
1. In the right pane, click the Win10-Clone.vmx file from the list of virtual machine files in the right
pane.
2. Click the Register VM icon.
The screenshot shows an example of registering the Win10-Clone.vmx file
On the Select a name and folder page, enter Win10-05.
3. In the Select a location for the virtual machine pane, expand SA-Datacenter and select the Lab
VMs folder.
4. Click Next.
5. In the Select a compute resource page, expand SA-Datacenter > Lab Servers.
6. Select sa-esxi-01.vclass.local and click Next.
7. On the Ready to Complete page, review the information and click Finish.
8. In the Navigator pane, click the VMs and Templates icon and verify that the Win10-05 virtual
machine is in the Lab VMs folder.

Task 3: Unregister and Delete Virtual Machines from the Datastore
You can remove a virtual machine from the vCenter Server Appliance inventory and delete all the
associated virtual machine files from the datastore, including the configuration file and the virtual disk
files.
1. In the Navigator pane right-click the Win10-05 virtual machine, select Delete from Disk, and click
Yes to verify the deletion.
2. Verify that the Win10-05 virtual machine no longer appears in the Navigator pane.
3. Click the Storage icon and verify that the folder and files where the Win10-05 virtual machine was
registered no longer exist.
4. Click the VMs and Templates icon.
Right-click the Photon-FromLib virtual machine, select Delete from Disk, and click Yes to verify
the deletion.

Task 4: Take Snapshots of a Virtual Machine
You take a snapshot to preserve the state and the data of a virtual machine at the time the snapshot is
taken. You use snapshots when you must revert to the same virtual machine state.
1. In the Navigator pane, right-click the Win10-03 virtual machine and select Open Remote Console.
2. You are logged in as vclass\administrator with the password VMware1!.
3. On the virtual machine desktop, drag the IOMETER file to the Recycle Bin.
4. Right-click the Recycle Bin icon and select Empty Recycle Bin to delete the IOMETER file
permanently.
5. Click Yes to verify the file deletion and leave the virtual machine console open.
6. Return to vSphere Client.
a. Click the VMware Remote Console icon in the Windows Tool bar.
 Clicking the VMware Remote Console icon minimizes the console window.
7. Right-click the Win10-03 virtual machine.
8. Select Snapshots > Take Snapshot.
a. The Take Snapshot wizard appears
9. Click OK and monitor the task in the Recent Tasks pane.
10. Click the VMware Remote Console icon to return to the virtual machine desktop.
11. On the virtual machine desktop, drag the CPUBUSY file to the Recycle Bin.
12. Right-click the Recycle Bin icon and select Empty Recycle Bin to delete the CPUBUSY file
permanently.
13. Click Yes to verify the file deletion and leave the virtual machine console open.
14. Return to vSphere Client.
15. Right-click the Win10-03 virtual machine and select Snapshots > Take Snapshot to take another
snapshot.
16. Configure the snapshot
17. 17. Click OK and monitor the task in the Recent Tasks pane.

Task 5: Add Files and Take Another Snapshot of a Virtual Machine
You add some files to a virtual machine and create another snapshot of the virtual machine. This
snapshot contain files that allow you to see how the virtual machines change when you revert to the
different snapshots in subsequent tasks.
1. Connect the ClassFiles-vSphere.iso file on the CD/DVD drive to the Win10-03 virtual machine.
a. Right-click the Win10-03 virtual machine and select Edit Settings.
b. Select Datastore ISO File from the CD/DVD drive 1 drop-down menu.
c. Select Class-Datastore in the left pane.
d. Select the Classfiles-vSphere.iso file in the middle pane.
e. Click OK.
f. Select the Connected check box for CD/DVD drive 1.
g. Click OK to close the Edit Settings dialog box.
2. Return to the Win10-03 virtual machine console.
3. Click the Windows Start icon and navigate to Windows System > This PC.
4. Click DVD Drive (D:) to view files.
5. Copy the CPUBUSY VBScript Script file from the D: drive to the virtual machine’s desktop.
6. Close the DVD Drive (D:) CDROM window.
7. Return to vSphere Client and disconnect the CD/DVD drive from the Win10-03 virtual machine.
a. From vSphere Client, right-click the Win10-03 virtual machine and select Edit Settings.
b. Select Client Device from the CD/DVD drive 1 drop-down menu and click OK.
8. Right-click the Win10-03 virtual machine and select Snapshots > Take Snapshot to take another
snapshot.
9. Configure the snapshot
10. Click OK.
11. Monitor the task in the Recent Tasks pane and wait for completion.
This task takes slightly longer than previous snapshots because the guest memory is also being
saved.
12. Right-click the Win10-03 virtual machine and select Snapshots > Manage Snapshots.
You should see three snapshots. The difference in icons is due to whether the Snapshot the virtual
machine’s memory check box was selected when the snapshot was taken.
13. Leave the Manage Snapshots open.
14. Close the Win10-03 virtual machine console.
a. Right click the VMware Remote Console icon in the Windows Tool bar and select Close
Window.
b. Close the empty browser tab

Task 6: Revert the Virtual Machine to a Snapshot
You revert a virtual machine to the state it had at the time when the selected snapshot was taken.
1. In Manage Snapshots, select the Without iometer or cpubusy snapshot and click Revert to.
2. Click OK to verify the revert.
3. Click Done to close Manage Snapshots.
Q1. Did the virtual machine power off and why?
1) Yes. The virtual machine powered off because the memory state was not preserved.
4. In the Navigator pane, right-click the Win10-03 virtual machine and select Power > Power On.
5. In the Navigator pane, right-click Win10-03 and select Open Remote Console.
Wait for the boot process to complete.

6. You are logged in as vclass\administrator with the password VMware1!.
Q2. Is either IOMETER or CPUBUSY on the desktop?
2) No. You removed these files before creating the snapshot named Without iometer or
cpubusy.
7. Close the Win10-03 virtual machine console.
8. In vSphere Client, right-click the Win10-03 virtual machine and select Snapshots > Manage
Snapshots.
The You Are Here pointer should be below the snapshot named Without iometer or cpubusy.
9. Select the With cpubusy snapshot on the Manage Snapshots tab and click Revert to.
10. Click OK to verify the revert operation.
11. Click Done to close Manage Snapshots.
 Q3. Did the virtual machine power off, and what is the reason?
3) No. The virtual machine did not power off because the memory state was preserved.
12. Open a console for the Win10-03 virtual machine.
 Q4. Is CPUBUSY on the desktop?
4) Yes.
 Q5. Is IOMETER on the desktop?
5) No

Task 7: Delete an Individual Snapshot
You can remove a snapshot on the Snapshots tab. The snapshot files are consolidated and written to the
parent snapshot disk.
1. Return to vSphere Client.
2. In the Navigator pane, right-click the Win10-03 virtual machine and select Snapshots > Manage
Snapshots.
The You are here pointer must be below the With cpubusy snapshot.
3. Select the Without iometer or cpubusy snapshot and click the DELETE button.
4. 4. Click OK to verify the deletion.
5. Click Done to close Manage Snapshots.
6. Q1. Did the virtual machine power off?
7. No.
8. Q2. In the virtual machine console, is the CPUBUSY file on the desktop?
9. Yes. The CPUBUSY file is still on the desktop because deleting the snapshot does not change
the virtual machine's current state. Deleting the snapshot removes the ability to return to that
snapshot's point in time.

Task 8: Delete All Snapshots
You can use the Delete All function to delete all the snapshots of a virtual machine.
1. In the Navigator pane, right-click the Win10-03 virtual machine and select Snapshots > Manage
Snapshots.
2. In Manage Snapshots click Delete All.
3. Click OK to verify that you want to delete all the remaining snapshots.
Only the You are here pointer should appear on the snapshots tab.
Q1. Were all the remaining snapshots deleted from the Manage Snapshots dialog box?
Yes.
4. Click Done to close Manage Snapshots.
5. Return to the Win10-03 virtual machine console.
Q2. Is CPUBUSY on the desktop, and why?
Yes. The current state of the virtual machine is not altered. Snapshots are consolidated and
then removed. An option to revert to those earlier points in time is no longer available.
6. Close the Win10-03 virtual machine console.
7. Close vSphere Client.
8. vSphere Web Client is used in the next lab.
9. Inform your instructor that you have completed this lab. If prompted, continue to the next lab

-------------------------------------- P7 -------------------------------------------------------
(A) Aim: In vCenter Server, create and use resource pools on an ESXi host
Objective: In this lab, you perform the following tasks:
1. Create CPU Contention
2. Create Resource Pools
3. Verify Resource Pool Functionality
In this lab, you use vSphere Web Client to perform the tasks.
Steps:
Task 1: Create CPU Contention
You use a tool to create CPU contention in your lab environment for testing. You force the virtual
machines to compete for and share the limited logical CPU resources on the ESXi host, which might
lead to performance degradation.
1. Open your Firefox Web browser, click vSphere Site-A on the favorite bar, and select vSphere Web
Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. vSphere Web Client opens to Hosts and Clusters.
4. In the Navigator pane, expand SA-Datacenter, the Lab Servers folder, and your ESXi hosts.
5. Verify that the Win10-02 and Win10-04 virtual machines are powered on and running on sa-esxi01.vclass.local.
6. 6. If necessary, migrate the virtual machines to sa-esxi-01.vclass.local.
7. Start the CPUBUSY script on the virtual machine desktops.
a. Right-click on Win10-02 and select Open Console.
b. Select Web Console, then click Continue in the Open Console panel.
c. You are logged in as vclass\administrator with the password VMware1!
d. On the desktop, right-click CPUBUSY and select Open with Command Prompt. This script
runs continuously. It stabilizes in 1 to 2 minutes. This script repeatedly does floating-point
computations. The script displays the duration (wall-clock time) of a computation, for
example, I did three million sines in # seconds.
e. Repeat steps a through d on the Win10-04 virtual machine. You can use the number of
seconds reported as a performance estimate. The program should run at about the same rate
in each virtual machine.
8. In the Navigator pane, right-click the Win10-02 virtual machine and select Edit Settings.
9. On the Virtual Hardware tab, click the arrow next to CPU.
10. In the Scheduling Affinity text box, enter 1.
a. This affinity setting forces the Win10-02 virtual machine to run only on logical CPU 1
11. Click OK.
a. CAUTION
b. CPU affinity is used mainly to create CPU contention for training purposes. The use of
this feature in a production environment is strongly discouraged.
12. Repeat steps 8 through 11 for the Win10-04 virtual machine.
13. Allow the CPUBUSY script to run for 1 or 2 minutes.
Task 2: Create Resource Pools
You use resource pools to delegate control over resources of the host or a cluster and to
compartmentalize all resources in a cluster.
1. Right-click sa-esxi-01.vclass.local in the Navigator pane and select New Resource Pool
2. Assign properties to the resource pool.
3. Click OK.
4. In the Navigator pane, right-click sa-esxi-01.vclass.local and select New Resource Pool.
5. Assign properties to the resource pool.
6. Click OK.
Task 3: Verify Resource Pool Functionality
You assign virtual machines to resource pools with different resource settings to monitor and compare
the performance differences.
1. Select the rp-Test resource pool in the Navigator pane and click the Summary tab.
2. In the Resource Settings pane, click the arrow next to CPU to expand the view.
Q1. What is the number of shares for this resource pool?
1. 2,000.
3. Select rp-Production in the Navigator pane and click the Summary tab.
4. View the Resource Settings pane.
Q2. What is the number of shares for this resource pool?
2. 8,000
5. Drag the Win10-02 virtual machine to the rp-Production resource pool.
6. Drag the Win10-04 virtual machine to the rp-Test resource pool.
7. Open each virtual machine console to monitor the results of the CPUBUSY script.
Allow several minutes for CPU contention to occur. If you are logged out of the console due to
inactivity, log in again as vclass\administrator with the password VMware1!.
Q3. What is the difference in performance between the two virtual machines?
3. The rp-Test resource pool, and the virtual machine in it, have only one-fourth of the
CPU shares that the rp-Production resource pool has. So the virtual machine in the rpTest resource pool receives only one-fourth of the CPU cycles of the logical CPU to
which the virtual machines are pinned.
8. In vSphere Web Client, change the CPU shares of the rp-Test resource pool from Low to
Normal.
a. Right-click the rp-Test resource pool in the Navigator pane and click Settings.
b. Verify that CPU Resources is selected and click Edit.
c. Select Normal from the Shares drop-down menu and click OK.
9. In each virtual machine console, allow the script to run for a few minutes and compare the
performance of the CPUBUSY script on each virtual machine.
As contention diminishes on the Win10-04 virtual machine, you see a difference in
performance.
10. Repeat step 8 to change CPU shares for the rp-Production resource pool from High to Normal.
As contention diminishes, you see performance balance between the two virtual machines.
11. Press Ctrl+C in the Command Prompt window to stop the CPUBUSY script in each virtual
machine console.
12. Close the Win10-02 and Win10-04 consoles.
13. Click the Home icon and select Home.
14. Leave vSphere Web Client open for the next lab.
15. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

(B) Aim: Use the system monitoring tools to reflect the CPU workload.
Objective: In this lab, you perform the following tasks:
1. Create the CPU Workload
2. Use Performance Charts to Monitor CPU Utilization
3. Undo Changes Made to the Virtual Machines
In this lab, you use vSphere Web Client to perform the tasks.
Steps:
Task 1: Create the CPU Workload
You run the CPUBUSY script in each virtual machine to create heavy CPU workload in your lab
environment for testing.
1. If vSphere Web Client is not active, open your Firefox web browser, click vSphere Site-A on the
favorite bar, and select vSphere Web Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. Click the Home icon and select VMs and Templates.
4. Expand the view of the Navigator pane.
5. Validate that the Win10-02 and Win10-04 virtual machines are powered on.
6. Open consoles for Win10-02 and Win10-04.
7. On each virtual machine desktop, right-click the CPUBUSY script file and select Open with
Command Prompt.
Task 2: Use Performance Charts to Monitor CPU Utilization
You use the performance charts to monitor the CPU, memory, disk, network, and storage metrics.
1. Return to vSphere Web Client.
2. In the Navigator pane, select the Win10-02 virtual machine.
3. Click the Monitor tab, click Performance and select Advanced in the middle pane. The real-time
CPU usage graph appears.
4. Click the Chart Options link.
 The Chart Options dialog box appears.
5. Verify that CPU is selected in the Chart Metrics pane.
6. 6. In the Timespan drop-down menu, verify that Real-time is selected.
7. In the Select object for this chart pane on the right, deselect the Win10-02 virtual machine check
box.
8. In the Select counters for this chart pane, click None to deselect all counters.
9. In the Select counters for this chart pane, select the Ready and Used check boxes and click OK.
The CPU/Real-time chart for the Win10-02 virtual machine opens.
10. Open a new tab in your Firefox web browser and click the vSphere Web Client shortcut.
11. Click the Home icon and select VMs and Templates and expand the view.
12. In the Navigator pane, select the Win10-04 virtual machine.
13. Repeat steps 3 through 9 to configure the CPU Performance graph for the Win10-04 virtual
machine.
14. In the web browser window for each virtual machine, point to the end of the line graph to view the
current CPU ready value.
15. Record the current CPU ready value for each virtual machine and leave the Performance Chart
windows open.
 • Win10-02 __________
 • Win10-04 __________
16. In each virtual machine console, press Ctrl+C in the Command Prompt window to stop the
CPUBUSY script. CAUTION This script must be stopped in each virtual machine. If the script is
left running, the next lab is affected.
17. In the vSphere Web Client browser window for each virtual machine, point to the end of the line
graph to view the current CPU ready value.
18. Wait for the chart to be updated and compare the CPU ready value with what you recorded in step
15.
Performance charts update every 20 seconds.
Q1. Did the CPU ready value change? If it did, what is the reason for the change?
Yes. After the scripts stop, the CPU Ready value decreases significantly because CPU
contention does not occur
Task 3: Undo Changes Made to the Virtual Machines
You revert the configuration changes made to each virtual machine.
1. Close the second vSphere Web Client tab and the two virtual machine consoles.
2. In the first vSphere Web Client tab, remove the scheduling affinity value on the Win10-02 virtual
machine.
a. In the Navigator pane, right-click the Win10-02 virtual machine and select Edit Settings.
b. Click the arrow next to CPU to expand the view.
c. In the Scheduling Affinity text box, delete the value 1 and click OK.
3. Repeat step 2 to remove the scheduling affinity value on the Win10-04 virtual machine.
4. Right-click the Win10-02 virtual machine, select Power > Shut Down the Guest OS.
5. Click Yes to verify the guest shut down.
6. Repeat steps 4 and 5 for the Win10-04 virtual machine.
7. Leave vSphere Web Client open for the next lab.
8. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

---------------------------- P8 -------------------------------------------
Aim: Use the vCenter Server Appliance alarm feature
Objective: In this lab, you will perform the following tasks
1. Create a Virtual Machine Alarm to Monitor a Condition
2. Create a Virtual Machine Alarm to Monitor an Event
3. Trigger Virtual Machine Alarms and Acknowledge the Alarms
4. Disable Virtual Machine Alarms
In this lab, you use vSphere Web Client to perform the tasks.
Steps:
Task 1: Create a Virtual Machine Alarm to Monitor a Condition
You create and use alarms to respond to selected events, conditions, and states that occur with objects
in the vCenter Server inventory.
1. If vSphere Web Client is not active, open your Firefox web browser, click vSphere Site-A on the
favorite bar, and select vSphere Web Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. Click the Home icon and select Hosts and Clusters
4. In the Navigator pane, right-click the Win10-02 virtual machine and select Alarms > New Alarm
Definition to open the New Alarm Definition wizard.
NOTE
Because you are creating an alarm for the Win10-02 virtual machine, this alarm monitors only that
virtual machine. If you set the alarm on an object higher in the vCenter Server inventory, the alarm
applies to multiple virtual machines. For example, if you create an alarm on the vCenter Server
Appliance object, the alarm applies to all the virtual machine
5. Enter VM CPU Usage - Win10-02 in the General page Alarm name text box and click Next.
6. On the Triggers page, click Add (the green plus sign) to add the trigger conditions.
7. 7. Click Next
8. In the Actions page, click Add (the green plus sign) to configure the action settings.
9. Click Finish.
10. In the Navigator pane, select the Win10-02 virtual machine and click the Monitor tab.
11. On the Issues tab and select Alarm Definitions.
12. Verify that the VM CPU Usage - Win10-02 alarm appears in the alarm list for the Win10-02 virtual
machine

Task 2: Create a Virtual Machine Alarm to Monitor an Event
You set up general alarm settings, alarm triggers, trigger reporting, and alarm actions to monitor and
react to a specified event.
1. In the Navigator pane, select SA-Datacenter, and click the Monitor tab.
2. On the Issues tab and select Alarm Definitions.
3. Click Add (the green plus sign) to add an alarm for the data center.
The New Alarm Definition wizard starts.
4. Configure the alarm settings in the New Alarm Definition wizard General page.
5. Click Next
6. On the Triggers page, click Add (the green plus sign) in the pane named Trigger if ANY of the
following events occur.
7. Select VM suspended from the Event drop-down menu.
8. Click Add (the green plus sign) to specify the conditions for the alarm trigger to fire
9. 9. Click Next.
10. Leave the default settings in the Actions page and click Finish.
11. Verify that the VM Suspended - Win10-02 alarm appears in the alarm list for the data center.
Task 3: Trigger Virtual Machine Alarms and Acknowledge the Alarms
You acknowledge an alarm to discontinue it and inform others that you are taking ownership of the
issue. Your acknowledged alarms are visible in the system. The alarms are neither cleared nor reset.
1. Power on the Win10-02 virtual machine.
2. In the Navigator pane, select the Win10-02 virtual machine.
3. On the Monitor tab, click Issues and select Triggered Alarms. The triggered alarms appear in this
pane.
4. Open the console for the Win10-02 virtual machine.
5. You are logged in to the Win10-02 virtual machine as vclass\administrator with the password
VMware1!.
6. Right-click CPUBUSY and select Open with Command Prompt.
7. Wait for at least 30 seconds before the alarm is triggered and the virtual machine is suspended
8. Return to vSphere Web Client, refresh the Triggered Alarms pane and verify that the VM Suspended
- Win10-02 alarm is triggered.
An entry for this alarm should appear in the Triggered Alarms list
9. Right-click the VM Suspended - Win10-02 alarm and select Reset to Green.
10. On the Monitor tab, click Tasks & Events and select Events in the middle pane. The description
Manually cleared alarm ‘VM Suspend - Win10-02 ’ from Red should appear in the list.
11. In the Navigator pane, right-click the suspended Win10-02 virtual machine and select Power >
Power On.
12. Reload and open the Win10-02 virtual machine console.
13. Press Ctrl+C at the command prompt to stop the CPUBUSY script.
14. Close the Win10-02 virtual machine console.
15. Right-click the Win10-02 virtual machine and select Power > Shut Down Guest OS.
16. Click Yes to verify the Guest Shut Down operation.
17. Verify that the red alert icon is removed from the Win10-02 virtual machine in the Navigator pane.
Task 4: Disable Virtual Machine Alarms
You disable system built-in alarms or the alarms that you defined for specific objects.
1. Disable the VM CPU Usage - Win10-02 alarm.
a. In the Navigator pane, select the Win10-02 virtual machine.
b. On the Monitor tab, click Issues and select Alarm Definitions.
c. Select the VM CPU Usage - Win10-02 alarm in the list. The VM CPU Usage - Win10-02
pane appears in the right pane.
d. Click Edit.
e. On the General page, deselect the Enable this alarm check box and click Finish
2. Disable the VM Suspended - Win10-02 alarm.
a. Select SA-Datacenter in the Navigator pane.
b. On the Monitor tab in the middle pane, click Issues and select Alarm Definitions.
c. Enter VM suspended in the search box.
d. Right-click the VM Suspended - Win10-02 alarm in the list and select Edit.
e. On the General page, deselect the Enable this alarm check box and click Finish.
3. Leave vSphere Web Client open for the next lab.
4. Inform your instructor that you have completed this lab. If prompted, continue to the next lab

-------------------------- P9 ------------------------------------------------------------------------
Aim: Use vSphere HA functionality
Objective: In this lab, you perform the following tasks:
1. Create a Cluster Enabled for vSphere HA
2. Add Your ESXi Hosts to the Cluster
3. Test the vSphere HA Functionality
4. View the vSphere HA Cluster Resource Usage
5. Manage vSphere HA Slot Size
6. Configure a vSphere HA Cluster with Strict Admission Control
7. Prepare for the Next Lab
In this lab, you use vSphere Web Client to perform the tasks.
Steps:
Task 1: Create a Cluster Enabled for vSphere HA
You create a VMware vSphere® High Availability cluster to group multiple ESXi hosts together, to
achieve higher levels of virtual machine availability than each ESXi host can provide individually.
1. If vSphere Web Client is not active, open your Firefox web browser, click vSphere Site-A on the
favorite bar, and select vSphere Web Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. Click the Home icon and select Hosts and Clusters.
4. Right-click the SA-Datacenter object in the Navigator pane and select New Cluster.
The New Cluster dialog box appears.
5. Configure the new cluster.
6. Leave the default settings for the other options and click OK.
7. In the Recent Tasks pane, monitor the progress as the cluster is created.
Task 2: Add Your ESXi Hosts to the Cluster
You plan the resources and networking architecture of your cluster, add hosts to it, and specify the
vSphere HA settings.
1. Add both ESXi hosts to the SA-Compute-01 cluster.
a. Drag sa-esxi-01.vclass.local to SA-Compute-01.
b. Drag sa-esxi-02.vclass.local to SA-Compute-01.
2. Click Yes in the Warning panel.
Your existing resource pools collapse into the cluster root resource pool.
3. Monitor the Recent Tasks pane and wait for the Configuring vSphere HA task to complete. If the
tasks do not appear in the Recent tasks pane, you can find them in the Task Console.
4. In the Navigator pane, select SA-Compute-01 and click the Monitor tab.
5. Click vSphere HA and select Summary in the middle pane.
The vSphere HA summary information appears.
6. Record the name of the master host. __________
Q1. Does the number of protected virtual machines match the number of powered-on virtual
machines in the cluster?
Yes. If both the hosts are added to the cluster and there are no errors on the cluster, the number
of protected VMs equal the number of powered-on VMs.
7. Select Heartbeat in the middle pane.
Q2. How many datastores are used to monitor heartbeat?
Two datastores. Both the datastores are shared by all of the hosts in the cluster. Therefore, they
are automatically selected for heartbeating.
8. In the middle pane, select Configuration Issues and review the errors that are displayed.
At this point, each ESXi host has a single management network port. vSphere HA still works if an
ESXi host is configured with one management network port, but a second management network
port is necessary for management network port redundancy.
9. Select sa-esxi-01.vclass.local in the Navigator pane and click the Configure tab.
10. In the middle pane, navigate to Networking and select VMkernel adapters.
11. Select the vMotion VMkernel adapter.
12. Click the Edit Settings icon.
13. 13. On the Port properties page, ensure that the vMotion check box is selected and select the
Management check box.
14. Click OK.
15. In the Navigator pane, right-click sa-esxi-01.vclass.local and select Reconfigure for vSphere HA.
NOTE
You might need to refresh vSphere Web Client to eliminate any obsolete alarm icons.
16. Repeat step 9 through 15 for sa-esxi-02.vclass.local.
17. In the Navigator pane, select SA-Compute-01 and click the Monitor tab.
18. Click Issues and select All Issues from the middle pane.
Q3. Are the previous management configuration issues still displayed?
The management network error messages disappear

Task 3: Test the vSphere HA Functionality
You set up vSphere HA to monitor the cluster environment and detect hardware failures. When an ESXi
host outage is detected, vSphere HA automatically restarts the virtual machines on the other ESXi hosts
in the cluster.
1. In the Navigator pane, select the master ESXi host that you recorded in task 2, step 6.
2. Click the VMs tab and ensure that Virtual Machines is selected.
3. Power on the Win10-02 virtual machine.
4. Record the name of one or more powered-on virtual machines on the master host. __________
5. In the Navigator pane, select SA-Compute-01.
6. On the Monitor tab, click vSphere HA and select Summary from the middle pane.
7. In the Virtual Machines pane, verify that the Protected field matches the number of powered-on
VMs within the cluster and that the Unprotected field value is 0.
Verifying that Virtual Machines Unprotected field value is 0 indicates that it is safe to reboot the
host.
8. Simulate a host failure by rebooting the master host in the cluster.
IMPORTANT
Ensure that you reboot the system. Do not shut down the system.
a. Right-click the master ESXi host and select Power > Reboot.
A warning message appears stating that you chose to reboot the host, which is not in
maintenance mode.
b. Enter Testing vSphere HA as the reason for rebooting and click OK.
9. On the Monitor tab, click Tasks & Events and select Events in the middle pane.
The cluster entries are sorted by time. Note the entries that appear when the host failure was
detected.
The initial messages from the hosts might show failures. These messages indicate that the virtual
machines on the downed host have failed. The virtual machines take 1 to 2 minutes to successfully
restart on the new host.
10. Wait for an additional 1 to 2 minutes for the ESXi host that you rebooted in step 5 to enter an error
state.
11. In the Navigator pane, select the ESXi host that is in an error state, indicated with a red error icon
12. Click the VMs tab.
Q1. Do you see the virtual machines that were running on the original master ESXi host, which
you recorded earlier?
No. The virtual machines previously running on the original master ESXi host are running on
the remaining host in the cluster.
13. In the Navigator pane, select SA-Compute-01.
14. On the Monitor tab, click vSphere HA.
15. In the middle pane, select Summary.
Q2. Has the master host changed?
Yes. The slave host is elected as the new master host.
16. Monitor the original master ESXi host in the Navigator pane until it is fully running again. It might
take 5 minutes for the original master host to become fully running.

Task 4: View the vSphere HA Cluster Resource Usage
You examine the CPU, memory, and storage I/O resource usage information of the cluster.
1. On the Monitor tab, click Resource Reservation.
2. 2. Select CPU from the middle pane and record the information for the cluster.
a. Total Reservation Capacity (GHz) __________
b. Used Reservation (GHz) __________
c. Available Reservation (GHz) __________
3. In the bottom pane, verify that the CPU reservation is not set on the virtual machines.
The Reservation column shows 0 (MHz).
4. In the middle pane, select Memory and record the information for the cluster.
• Total Reservation Capacity (GB) __________
• Used Reservation (GB) __________
• Available Reservation (GB) __________
5. In the bottom pane, verify that the memory reservation is not set on the virtual machines. The
Reservation column shows 0 (MB).
Task 5: Manage vSphere HA Slot Size
You configure admission control to ensure that sufficient resources are available in a cluster to provide
failover protection and to ensure that the virtual machine resource reservations are respected.
1. In the Navigation pane, right-click SA-Compute-01 and select Settings.
2. Navigate to Services, and select vSphere Availability.
The Edit Cluster Settings wizard opens.
3. In the right pane, click Edit.
4. In the left pane, select Admission Control.
5. In the Define host failover capacity by drop-down menu, select Slot Policy (powered-on VMs) and
click OK.
6. In the right pane, click the Monitor tab.
7. Click vSphere HA, and select Summary from the middle pane.
8. In the right pane, scroll down to the Advanced Runtime Info pane and record the slot information
for this cluster.
a. Slot size: CPU __________ (MHz), Memory __________ (MB)
b. Total slots in cluster __________
c. Used slots __________
d. Available slots __________
e. Failover slots __________
9. In the Navigator pane, click the VMs and Templates icon.
10. Expand SA-Datacenter > Lab VMs, and power on the Win10-04 virtual machine.
11. Set the CPU reservation on the Win10-04 virtual machine.
a. Right-click the Win10-04 virtual machine and select Edit Settings.
b. Click the arrow next to CPU to expand the view.
c. In the Reservation text box, enter 512 (MHz) and click OK.
12. In the Navigator pane, click the Hosts and Clusters icon.
13. In the Navigator pane select SA-Compute-01.
14. Return to the Advanced Runtime Info pane and view the slot information for this cluster.
a. In the Advanced Runtime Info pane, verify that the slot size for the CPU changed from the
value recorded in step 8.
b. Record the information shown in the Slot size text box. Slot size: CPU __________ (MHz),
Memory __________ (MB)
15. Use the vSphere HA slot size policy to enforce a slot size.
a. In the Navigator pane, right-click SA-Compute-01 and select Settings.
b. In the middle pane select vSphere Availability and click Edit. The Edit Cluster Settings
wizard opens.
c. In the left pane, select Admission Control.
d. In the Define host failover capacity by pane, click Fixed slot size
e. In the CPU slot size text box, enter 300 (MHz) to change the CPU slot size.
f. Click Calculate next to VMs requiring multiple slots, then click the View link.
 The VMs Requiring Multiple Slots window appears
g. Record the Required Slots value for the Win10-04 virtual machine. __________
Because the CPU slot size has a fixed value of 300 MHz, the Win10-04 virtual machine
with the 512 MHz CPU reservation uses two slots to power on.
h. Click Close and click OK to exit the Edit Cluster Settings window.
16. View the slot information for the SA-Compute-01 cluster.
a. Return to the Advanced Runtime Info pane, record the information shown in the Slot size
text box and compare with the values recorded earlier.
Slot size: CPU __________ (MHz), Memory __________ (MB)
17. Remove the vSphere HA fixed slot size setting.
a. In the Navigator pane, right-click SA-Compute-01 and select Settings.
b. In the middle pane, select vSphere Availability and click Edit. The Edit Cluster Settings
wizard opens.
c. In the left pane, select Admission Control.
d. In the Define host failover capacity by pane, select Cover all powered-on virtual machines
for the slot size policy.
e. Click OK.
18. Remove the CPU reservation on the Win10-04 virtual machine.
a. In the Navigator pane, right-click the Win10-04 virtual machine and select Edit Settings.
b. Click the arrow next to CPU to expand the view.
c. Enter 0 (MHz) in the Reservation text box and click OK

Task 6: Configure a vSphere HA Cluster with Strict Admission Control
You use admission control to impose constraints on resource usage and ensure that sufficient resources
are available in a cluster to provide failover protection. Any actions violating the constraints are not
permitted.
In the previous task, when you configured the cluster under Define host failover capacity, you
configured vSphere HA to calculate slots. vSphere HA calculates the space for a virtual machine to run
based on the largest CPU and memory reservation across all powered-on virtual machines in the cluster.
This feature is called strict admission control.
1. Shut down the Guest OS for all the virtual machines.
2. 2. Verify the shut down operation and wait for the process to compete. Wait another minute for the
system to release the memory.
3. In the Navigator pane, select SA-Compute-01 and click the Summary tab.
4. Record the memory information for this cluster.
i. Capacity (total) __________
ii. Used __________
iii. Free __________
 Your view should be similar to the screenshot.

Q1. Why is the free memory value for the cluster less than the total memory capacity value?
Less memory is available because of the overhead needed to run VMkernel. VMkernel
is holding back memory for its own use.
5. Click the Monitor tab, click Resource Reservation, and select Memory in the middle pane.
6. Assign a 2000 MB memory reservation to the Win10-02 virtual machine.
a. In the lower pane, right-click the Win10-02 virtual machine and select Edit Resource
Settings.
b. In the Memory memory pane, enter 2000 (MB) in the Reservation text box and click OK.
c. Repeat steps a through c to set the memory reservation on the Win10-03 and Win10-04
virtual machines.
7. On the Monitor tab, and click vSphere HA.
8. Select Summary in the middle pane.
9. In the Advanced Runtime Info pane, record the value shown in the Total slots in cluster text box.
 Q2. Why does vSphere Web Client report N/A as the value?
vSphere Web Client reports N/A for the total number of slots because no virtual machines are
powered on yet. The slot size calculation considers only virtual machines that are powered on.
10. In the Navigator pane, right-click the Win10-02 virtual machine and select Power > Power On.
11. Return to the Advanced Runtime Info pane of SA-Compute-01 and click Refresh in the lower-right
corner of the pane.
12. Record the slot size values that appear.
13. View the effect that powering on this virtual machine has on your cluster.
Q3. How many total slots in the cluster, used slots, available slots, and failover slots do you
see?
You should see 4 total slots in the cluster: one used slot, one available slots, and 2 failover slots.
If you do not see 4 slots, refresh vSphere Web Client after 2 minutes and the numbers should
get updated. 
NOTE
The Advanced Runtime Info pane might display a smaller number of available slots in the cluster than
you expect.
Slot size is calculated using the largest reservations plus the memory overhead of any powered on virtual
machines in the cluster. However, vSphere HA admission control considers only the resources on a host
that are available for virtual machines. This amount is less than the total amount of physical resources
on the host, because some overhead exists.
Q4. How is the memory slot size calculated?
Unlike the CPU slot size calculation, which is based solely on the largest CPU reservation, the
calculation for memory slot size is based on the largest memory reservation, plus memory
overhead.
14. In the Navigator pane, right-click the Win10-04 virtual machine and select Power > Power On.
15. Return to the Advanced Runtime Info pane of SA-Compute-01 and click Refresh.
16. View the slot information.
Q5. How many slots are available and what is the reason?
Zero slots are available. Only two slots were available, the rest were marked as failover slots.
Because two virtual machines were powered on, each using one of the available slots, no more
slots are available.
17. In the Navigator pane, right-click the Win10-03 virtual machine and select Power > Power On.
18. Monitor the Recent tasks pane.
Q6. Is your virtual machine allowed to power on, and what is the reason?
The Win10-03 virtual machine is not allowed to power on. If a cluster does not have sufficient
resources to provide failover protection, the virtual machine does not power on resulting in an
error.

Task 7: Prepare for the Next Lab
You remove the memory reservations on virtual machines and disable admission control when they are
no longer needed.
1. Remove the memory reservation on each of the virtual machines.
a. Right-click the Win10-02 virtual machine and select Edit Resource Settings.
b. In the Memory section, enter 0 (MB) in the Reservation text box and click OK.
c. Repeat steps a and b to remove the memory reservation on the Win10-03 and Win10-04
virtual machines.
2. In the Navigator pane, right-click the Lab Servers folder and select Remove from Inventory.
3. Click Yes to verify the operation.
4. Edit the settings of the cluster to allow the number of running virtual machines to exceed the failover
capacity of the cluster.
a. In the Navigator pane, right-click SA-Compute-01 and select Settings.
b. In the middle pane, select vSphere Availability and click Edit. The Edit Cluster Settings
wizard opens. c. In the left pane, click Admission Control. d. From the Define host failover
capacity by drop-down menu, select Disabled. e. Click OK to commit your changes.
5. Right-click the Win10-03 virtual machine in the Navigator pane and select Power > Power On.
6. Leave vSphere Web Client open for the next lab.
7. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

------------------------------------------ P10-----------------------------------------------
(A)Aim : Implement a vSphere DRS cluster
Objective: In this lab, you perform the following tasks:
1. Create a Load Imbalance
2. Create a vSphere DRS Cluster
3. Verify Proper vSphere DRS Cluster Functionality
4. Create, Test, and Disable a VM-VM Affinity Rule
5. Create, Test, and Disable an Anti-Affinity Rule
6. Create, Test, and Disable a VM-Host Affinity Rule
In this lab, you use vSphere Web Client to perform the tasks.
Steps:
Task 1: Create a Load Imbalance
You create a load imbalance across the ESXi hosts in the SA-Compute-01 cluster to test how VMware
vSphere® Distributed Resource Scheduler™ works.
1. If vSphere Web Client is not active, open your Firefox Web browser, click vSphere Site-A on the
favorite bar, and select vSphere Web Client (SA-VCSA-01).
2. Log in with the user name administrator@vsphere.local and the password VMware1!.
3. Click the Home icon and select Hosts and Clusters.
4. Select sa-esxi-01.vclass.local. 114 Lab 17 Implementing vSphere DRS Clusters
5. On the VMs tab, if virtual machines are present on sa-esxi-01.vclass.local, migrate the virtual
machines to sa-esxi-02.vclass.local.
IMPORTANT: Change compute resource only when migrating VMs.
6. In the Navigator pane, select sa-esxi-02.vclass.local.
7. On the VMs tab, click Virtual Machines.
Compare the list of VMs shown in the list to the VMs shown in the Navigator pane.
8. Ensure that all the VMs are powered on.
9. Start the CPUBUSY script on each of the virtual machines.
a. Right-click Win10-02 and select Open Console.
b. You are logged in as vclass\administrator with the password VMware1!
c. Right-click the CPUBUSY script on each virtual machine’s desktop and select Open with
Command Prompt.
The number of running CPUBUSY instances required to cause vSphere DRS to migrate virtual
machines to another host varies, depending on the resource capacity of the lab infrastructure.
c. Repeat steps a through c for Win10-03 and Win10-04.
Task 2: Create a vSphere DRS Cluster
You create a vSphere DRS cluster to balance the computing capacity among all the ESXi hosts and the
associated virtual machines without service interruption.
1. In the Navigator pane, right-click the SA-Compute-01 cluster and select Settings.
2. Select vSphere DRS from the middle pane.
3. Click Edit. The Edit Cluster Settings wizard opens.
4. Select the Turn On vSphere DRS check box.
5. Select Manual from the DRS Automation drop-down menu.
6. Click the arrow next to DRS Automation to expand the view and move the Migration Threshold
slider to Aggressive, which is to the right side of the slider.
7. Leave other settings at their default values and click OK.
Task 3: Verify Proper vSphere DRS Cluster Functionality
You can run vSphere DRS in either manual, partially automated, or fully-automated modes. In the
manual mode, you review the recommendations for optimal virtual machine placement provided by
vSphere DRS and decide whether to make the changes.
1. Click the Monitor tab and click vSphere DRS.
If you do not see the expected buttons, refresh vSphere Web Client.
2. Click Run DRS Now.
Clicking the button forces vSphere DRS to immediately evaluate the cluster and provide
recommendations instead of waiting for the standard 5 minutes before generating
recommendations.
3. Click the Summary tab and click the arrow next to vSphere DRS to expand the pane.
The screenshot shows the expanded view of the vSphere DRS pane.
Q1. Does the gauge show that the load is imbalanced?
Yes. Because all the virtual machines are running on a single host and the running CPUBUSY
instances create a large CPU load.
4. Click the Monitor tab, on vSphere DRS, and select CPU Utilization.
5. In the Sum of Virtual Machine CPU Utilization - Per Host pane, view the CPU consumption on
each ESXi host and click each of the colored boxes to view the CPU consumption of each virtual
machine.
The screenshot shows the CPU utilization information of the ESXi host and the virtual machine.
6. In the middle pane, select Recommendations and view the vSphere DRS recommendations.
The screenshot shows a sample recommendation made by vSphere DRS to migrate a virtual
machine from one host to another host.
If vSphere DRS recommendations do not appear, refresh vSphere Web Client.
7. Click Apply Recommendations.
If your recommendations have expired, click Run DRS Now to generate new recommendations and
apply them.
If new recommendations do not appear, refresh your browser.
You may need to click Run DRS Now and click Apply Recommendations the second time.
8. On the Monitor tab and click Tasks & Events.
9. Select Tasks in the middle pane.
10. Click the Expand All icon.
11. 11. Monitor the Migrate virtual machine task until completion
12. Click vSphere DRS and click Run DRS Now to force vSphere DRS to evaluate the cluster status.
Q2. Is any recommendation shown?
No. Because all recommendations are applied.
13. Click the Summary tab and view the vSphere DRS pane.
Q3. Does the gauge show that the load is balanced?
The resource allocation balance improves after applying the vSphere DRS recommendations.
14. Click the Monitor tab and click the vSphere DRS tab.
15. Select CPU Utilization.
The virtual machines should spread across the two ESXi hosts. You can refresh the screen to see
the result.
16. In each virtual machine console, press Ctrl+C to stop the CPUBUSY script. 17. Close the virtual
machine consoles.
Task 4: Create, Test, and Disable a VM-VM Affinity Rule
You use VM-VM affinity rules to specify whether the selected individual virtual machines should run
on the same host or be kept on separate hosts.
1. In the Navigator pane, select SA-Compute-01 and click the VMs tab.
2. Point to the gray row of column names, right-click the row, and select Show/Hide Columns.
3. Select the Host check box from the list and click OK.
The Host column appears in the table.
You can drag the Host column to the left so that it is easily visible.
4. Based on the information in the Name and Host columns, verify that all the virtual machines are
not running on a single ESXi host.
Having virtual machines reside on two different ESXi hosts is necessary to test the validity of the
VM/Host rule that you create in the later steps. If you have one virtual machine on each ESXi host
in the cluster, no action is necessary.
5. In the Navigator pane, right-click SA-Compute-01 and select Settings.
6. Select VM/Host Rules in the middle pane.
7. In the VM/Host Rules pane, click Add. The Create VM/Host Rule dialog box appears.
8. Configure the options for the VM/Host rule.
a. In the Name text box, enter Colocate-Win10-VMs.
b. Leave the Enable rule check box selected.
c. From the Type drop-down menu, select Keep Virtual Machines Together.
d. Click Add to add members.
e. Select the check boxes for the Win10-02 and Win10-03 virtual machines and click OK.
9. Click OK to close the Create VM/Host Rules dialog box.
10. Click the Monitor tab and click vSphere DRS.
11. Select Recommendations and click Run DRS Now.
Q1. Do you see any recommendations, and why?
Yes. vSphere DRS recommends that the two virtual machines be migrated to other hosts.
The first recommendation moves Win10-03 off of the sa-esxi-01.vclass.local to maintain cluster
balance.
The second migration is based on the vSphere DRS affinity rule that you created. The migrate
Win10-04 recommendation is assigned priority 1 because it is attempting to fix a broken affinity
rule. Therefore, even if vSphere DRS was configured to Conservative, this recommendation
would appear.
12. Click Apply Recommendations and wait for the virtual machine migrations to complete.
The virtual machines associated with your affinity rule should be migrated to one of the two hosts
in the vSphere DRS cluster.
13. Click the Monitor tab and click Tasks & Events to view the progress of the virtual machine
migration and wait for its completion.
14. Click the VMs tab.
15. Click the Host column heading to sort the virtual machines by the ESXi host on which they reside
The Win10-02 and Win10-03 virtual machines should be running on the same ESXi host.
16. Click the Configure tab, and select VM/Host Rules in the middle pane.
17. In the VM/Host Rules pane, select your affinity rule and click Edit above the rule.
18. Deselect the Enable rule check box and click OK.
Task 5: Create, Test, and Disable an Anti-Affinity Rule
You create a vSphere DRS anti-affinity rule to force the specified virtual machines to be kept on
separate hosts.
1. In the VM/Host Rules pane, click Add
2. 2. Configure the options for this VM/Host rule.
a. In the Name text box, enter Separate-Win10-VMs.
b. Keep the Enable rule check box selected.
c. From the Type drop-down menu, select Separate Virtual Machines.
d. Click Add.
e. Select the check boxes for the Win10-02 and Win10-03 virtual machines own and click
OK.
3. Click OK to close the Create VM/Host Rules dialog box.
4. Click the Monitor tab and click vSphere DRS.
5. In Recommendations and click Run DRS Now.
If new recommendations do not appear, refresh vSphere Web Client.
The new recommendation is marked as priority 1 as a result of your vSphere DRS rules.
6. Click Apply Recommendations.
7. Click the Monitor tab and click Tasks & Events to view the progress of the virtual machine
migration and wait for the virtual machine migration to complete before you proceed to the next
step.
8. Click the VMs tab.
9. View the information shown in the Host column.
As a result of your anti-affinity rule, you should see that the virtual machines associated with your
anti-affinity rule are placed on two different ESXi hosts.
10. Click the Configure tab and return to VM/Host Rules.
11. In the VM/Host Rules pane, select the Separate-Win10-VMs rule.
12. Click Delete above the pane and click Yes to verify the deletion.
Task 6: Create, Test, and Disable a VM-Host Affinity Rule
You use VM-Host affinity rules to specify whether the members of a selected virtual machine vSphere
DRS group can run on the members of a specific host vSphere DRS group.
1. In the middle pane, select VM/Host Groups.
2. In the VM/Host Groups pane, click Add.
3. In Create VM/Host Group dialog box, configure the options for this rule.
a. In the Name text box, enter Win10-VMs.
b. Verify that VM Group is selected from the Type drop-down menu.
c. Click Add.
d. Select the check boxes for the Win10-03 and Win10-04 virtual machines.
e. Click OK.
f. Click OK to close the dialog box.
4. In the VM/Host Groups pane, click Add.
5. When the Create VM/Host Group dialog box appears, configure the options.
a. In the Name text box, enter Win10-Host.
b. From the Type drop-down menu, select Host Group.
c. Click Add.
d. Select the check box for sa-esxi-02.vclass.local and click OK.
e. Click OK to close the dialog box.
6. Select VM/Host Rules in the middle pane.
7. In the VM/Host Rules pane, click Add.
8. When the Create VM/Host Rules dialog box appears, configure the options.
a. In the Name text box, enter Run-only-on-host2.
b. Keep the Enable rule check box selected.
c. From the Type drop-down menu, select Virtual Machines to Hosts.
d. From the VM Group drop-down menu, select Win10-VMs.
e. Select Must run on hosts in group from the drop-down menu.
f. From the Host Group drop-down menu, select Win10-Host.
g. Click OK to close the dialog box.
9. Click the Monitor tab and click vSphere DRS.
10. Select Recommendations in the middle pane and click Run DRS Now.
Q1. What recommendations did vSphere DRS make and why?
1. vSphere DRS recommends that one of your Win10 virtual machine be migrated to a different
host due to the violation of your VM/Host affinity rule. The other Win10 virtual machine is
already running on the second host.
11. If there are recommendations, click Apply Recommendations.
12. Click the Monitor tab and click Tasks & Events to view the progress of the virtual machine
migration and wait for its completion.
The Win10 virtual machines are migrated as necessary so that they both reside on the second ESXi
host.
13. Click the VMs tab.
14. 14. Click the Host column heading to sort the virtual machines by the ESXi host on which they reside.
Your Win10-03 and Win10-04 virtual machines that were running on different ESXi hosts are both
running on sa-esxi-02.vclass.local.
15. In the Navigator pane, right-click the Win10-03 virtual machine and select Migrate. The Migrate
wizard starts.
16. On the Select the migration type page, click Change computer resource only and click Next.
17. On the Select a compute resource page, click Clusters and click SA-Compute-01.
In the Compatibility pane, you might notice the Virtual machine 'Win10-03' on host 'sa-esxi01.vclass.local' would violate a virtual machine - host affinity rule message.
This issue is due to a conflict of the rules that you created and your migration attempt
18. Click Cancel to cancel the migration.
19. Return to the Configure tab, and select VM/Host Rules in the middle pane.
20. In the VM/Host Rules pane, select your Run-only-on-host2 rule and click Edit above the rule.
21. Deselect the Enable rule check box and click OK.
22. Leave vSphere Web Client open for the next lab.
23. Inform your instructor that you have completed this lab. If prompted, continue to the next lab.

(B) Aim: Install, configure, and use vSphere Update Manager.
Objective: In this lab, you perform the following tasks:
1. Modify the Cluster Settings
2. Configure vSphere Update Manager
3. Create a Patch Baseline
4. Attach a Baseline and Scan for Updates
5. Stage the Patches onto the ESXi Host
6. Remediate the ESXi Host
In this lab, you use vSphere Web Client to perform the tasks.
Steps:
Task 1: Modify the Cluster Settings
You enable vSphere DRS in the fully-automated mode so that vSphere DRS determines the best possible
distribution of virtual machines among your ESXi hosts and automatically performs the migration.
1. On the vSphere Web Client Home page, select Hosts and Clusters.
2. If not already selected, select SA-Compute-01 in the Navigator pane.
3. Right-click SA-Compute-01 and select Settings.
4. Select vSphere DRS and click Edit.
The Edit Cluster Settings dialog box appears.
5. On the vSphere DRS page, select Fully Automated from the DRS Automation drop-down menu.
This operation enables vSphere DRS to migrate virtual machines as necessary without asking
permission from an administrator.
6. In the left pane of the Edit Cluster Settings window, select Admission Control.
7. Verify that Disabled is selected from the Define Host Failover capacity By drop-down menu.
8. Click OK.
9. Click the Monitor tab for SA-Compute-01, then click the Resource Reservation tab.
10. Select CPU and review the Reservation (MHz) column to verify that no CPU reservations are
assigned to virtual machines.
11. Select Memory and review the Reservation (MB) column to verify that no memory reservations are
assigned to virtual machines.
CAUTION Removing CPU and memory reservations is necessary in this lab environment for
training purposes. In a production environment, you might not need to remove them.
Task 2: Configure vSphere Update Manager
You can import patches and extensions manually by using an offline bundle, or you can use a shared
repository or the Internet as the download source for patches and extensions.
1. Click the Home icon and select Update Manager.
2. In the Navigator pane, select sa-vcsa-01.vclass.local.
3. In the right pane, click the Manage tab.
4. In the middle pane, select Download Settings.
5. In the Download Settings pane, click Import Patches.
6. Click Browse, navigate to the Desktop\Class Materials and Licenses\Class Folder, select the
ESXi670-2018xxxxx.zip file, and click Open.
7. Wait until the patch bundle has been uploaded and the Patch file upload is successful message is
displayed.
8. Click Next.
9. If a security warning appears, select the Install this certificate and do not display any security
warnings check box and click Ignore.
10. When the import operation is complete, click Finish.
Task 3: Create a Patch Baseline
You create a baseline to specify the requirements that should be met by vSphere objects, such as virtual
machines, ESXi hosts, or virtual appliances. Your patch baseline contains a collection of patches,
extensions, or upgrades.
1. Click the Hosts Baselines tab, and click New Baseline to open the New Baseline wizard.
2. On the Name and Type page, enter ESXi Host Update in the Name text box.
3. In the Description text box, enter Patch for ESXi Host 6.7 and click Next
4. 4. On the Patch Options page, click Fixed and click Next.
5. On the Patches page, select all patches from the list.
6. Click Next.
7. On the Ready to Complete page, click Finish
Task 4: Attach a Baseline and Scan for Updates
You use scanning to evaluate a set of hosts, virtual machines, or virtual appliances against the patches,
extensions, and upgrades that are included in the attached baselines and baseline groups.
1. On the top-right corner of the Baselines tab, click Go to compliance view.
2. 2. In the Navigator pane, select sa-esxi-02.vclass.local and click the Update Manager tab in the right
pane
3. Click Attach Baseline. The Attach Baseline or Baseline Group dialog box appears.
4. Select the ESXi Host Update check box and click OK.
5. Click Scan for Updates.
6. In the Scan for Updates window, verify that the Patches and Extensions and Upgrades check boxes
are both selected and click OK.
7. Monitor the Recent Tasks pane and wait for the scan to complete.
8. Select the ESXi Host Update baseline in the Baseline list and verify that the ESXi host is listed as
noncompliant in the center bottom pane.

Task 5: Stage the Patches onto the ESXi Host
You stage patches and extensions onto the ESXi hosts so that they are available locally when the
remediation process takes place. This method speeds up remediation.
1. In vSphere Web Client, if not already selected, select sa-esxi-02.vclass.local in the Navigator
pane.
2. In the right pane, click Stage Patches.
The Stage wizard starts
3. On the Baselines page, select the ESXi Host Update baseline and click Next.
4. On the Hosts page, verify that the sa-esxi-02.vclass.local host is selected and click Next.
5. On the Patches and Extension page, accept the default settings and click Next.
6. On the Ready to Complete page, review the information and click Finish.
7. Monitor the Recent Tasks pane for the staging tasks to complete.
Task 6: Remediate the ESXi Host
You temporarily disable cluster features, such as VMware vSphere® Distributed Power Management™
in the cluster and apply the patches to the ESXi host.
1. In vSphere Web Client, if not already selected, select sa-esxi-02.vclass.local in the Navigator pane.
2. In the right pane, click Remediate. The Remediate wizard starts.
3. On the Select Baselines page, select the ESXi Host Update baseline and click Next.
4. On the Select Target objects page, verify that sa-esxi-02.vclass.local is selected and click Next.
5. On the Patches and Extensions page, leave the default settings and click Next.
6. On the Advanced Options page, select the Schedule this action to run later check box.
7. Enter Remediate sa-esxi-02 ESXi host on SA-Compute-01 in the Task Name text box
8. For Remediation Time, enter a time that is 3 minutes from the current time and leave the other
settings at their default values.
9. Click Next.
10. On the Host Remediation Options page, select the Disable any removeable media devices connected
to the virtual machines on the host check box and leave the other settings at their default values.
11. Click Next.
12. On the Cluster Remediation Options page, deselect the Disable Distributed Power Management
(DPM) if it is enabled for any of the selected clusters check box and click Next. 13. On the Ready
to Complete page, review the information and click Finish.
13. Monitor the Recent Tasks pane. If the expected results are not seen, refresh vSphere Web Client.
Q1. Was the ESXi host patched successfully?
Yes.
14. Close vSphere Web Client.
This is the last VMware vSphere 6.7 Install, Configure, Manage lab.
15. Inform your instructor that you have completed all labs for this class
