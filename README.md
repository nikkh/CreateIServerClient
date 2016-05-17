"# CreateIServerClient" 

This template will generate an IServer client machine for use in the IServer POC.  When you click the 'deploy to azure' button below, you will need to log in to the Azure Maangement portal.  You can only do this if you log into the portal with an account that is associated with an MSDN subscription.  To do this using any other type of subscription is not permitted by Windows Client LIcencing rules.

In order to successfully run the template you will need to provide the key of the storage account where the template image resides.  Without the correct key the template deployment will fail.  Please do not distribute this key to friends or colleagues.

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnikkh%2FCreateIServerClient%2Fmaster%2FCreateIServerClient%2FTemplates%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fnikkh%2FCreateIServerClient%2Fmaster%2FCreateIServerClient%2FTemplates%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

This template allows you to create a new Virtual Machine from a custom image that contains Windows 7 client, IServer Client pre-configured and a utility directory that contains a VPN client and further instructions on how to join your POC client to the ispoc.local domain.  Once your client machine is up and running, please change directory to C:\ispoc and follow the instructions in readme.doc.

# What does this template do?</h1>

Basically it creates two VMs, one that is the transfer virtual machine and the second that is the actual virtual machine that is the goal of the deployment. Transfer VM can be removed later.

The process of this template is:

1. A Virtual Network is deployed
2. Virtual NICs for both Virtual Machines
3. Storage Account is created
3. Transfer Virtual Machine gets deployed
4. Transfer Virtual Machine starts the custom script extension to start the VHD copy from source to destination storage acounts
5. The new Virtual Machine based on a custom image VHD gets deployed 

If you already have a virtual newtwork in your subscription you can override the address space for the ispocClientVet on the parameters screen that is displayed when you click deploy.
