<p class="has-line-data" data-line-start="0" data-line-end="1">Follow Prerequisties from the link : <a href="https://github.com/Azure/caf-terraform-landingzones/blob/master/documentation/getting_started/getting_started.md">Instructions of Azure Landing Zones</a></p>
<p class="has-line-data" data-line-start="2" data-line-end="3"><a href="https://github.com/Azure/caf-terraform-landingzones.git">AZLandingZones</a>(“Use This Repo”)</p>
<ol>
<li class="has-line-data" data-line-start="4" data-line-end="5">Download &amp; Install Git bash</li>
<li class="has-line-data" data-line-start="5" data-line-end="6">Clone Git hub repo in local system (git clone <a href="https://github.com/Mohammed-Sohail/AzLandingZones.git">https://github.com/Mohammed-Sohail/AzLandingZones.git</a>) using cmd or git cli</li>
<li class="has-line-data" data-line-start="6" data-line-end="7">Download &amp; Install vs code</li>
<li class="has-line-data" data-line-start="7" data-line-end="8">Open cloned Repository in vs code</li>
<li class="has-line-data" data-line-start="8" data-line-end="9">Install Remote Development Extension in vs code</li>
<li class="has-line-data" data-line-start="9" data-line-end="10">Press ctrl+shift+p in vs code to open command palette and search for “Open Workspace for Containers” and select the same.</li>
<li class="has-line-data" data-line-start="10" data-line-end="11">run cmd “rover login -t [TENANT_ID/TENANT_NAME] -s [SUBSCRIPTION_GUID]” in your vs code terminal.</li>
<li class="has-line-data" data-line-start="11" data-line-end="12">run cmd “az account set --subscription &lt;subscription_GUID&gt;” in your vs code terminal.</li>
<li class="has-line-data" data-line-start="12" data-line-end="14">Execute launchpad by running cmd “rover -lz /tf/caf/caf_launchpad -launchpad -var-folder /tf/caf/caf_launchpad/scenario/200 -parallelism=30 -a apply”</li>
</ol>
<p class="has-line-data" data-line-start="14" data-line-end="21"><strong>why launchpad is used?</strong><br>
The launchpad allows you to manage the foundations of landing zone environments by:<br>
* Securing remote Terraform state storage for multiple subscriptions.<br>
* Managing the transition from manual to automated environments.<br>
* Bring up the DevOps foundations using Azure DevOps, Terraform Cloud and GitHub actions<br>
–&gt; The launchpad tries to retrieve an existing terraform state on Azure using the name of the tfstate file and the name of the workspace (level-0 by default)<br>
–&gt; Creates a tfstates folder if no remote state have been retrieved, this happens when your environment does not contain a storage account containing a tfstate matching the input parameters</p>
<ol start="10">
<li class="has-line-data" data-line-start="22" data-line-end="26">To Run Customized tf script<br>
-&gt;run cmd “rover login -t [TENANT_ID/TENANT_NAME] -s [SUBSCRIPTION_GUID]” in your vs code terminal.<br>
-&gt;rover -lz /tf/caf/landingzones/caf_solution/ -var-folder /tf/caf/RootDir/SubDir/Example.tf -tfstate SubDir.tfstate -env Dev -level level3 -a [plan|apply|destroy]</li>
</ol>
<p class="has-line-data" data-line-start="26" data-line-end="28"><strong>Why Rover is Used?</strong><br>
Rover is a container which comes with all the dependencies(terraform,docker) installed to run our tf scripts in that defined environment</p>
<p class="has-line-data" data-line-start="30" data-line-end="37">RootDir<br>
|<br>
Parent<br>
|<br>
SubDir<br>
|<br>
<a href="http://Example.tf">Example.tf</a></p>
