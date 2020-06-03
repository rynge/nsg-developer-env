## Getting Started

Development is done on the SDSC Cloud. To access the cloud dashboard,
follow [this link](https://dashboard.cloud.sdsc.edu/). You will log in
with the username and password given to you by NSG.

## Adding an SSH Key
Before launching any instances, you should upload an SSH key so that you can authenticate with them. Navigate to the **Key Pairs** page by going to **Project** ->
**Compute** -> **Key Pairs** in the navigation menu on the left.

![Key pairs page web view](key_pairs.PNG)

You can either create a key pair using the dashboard or upload an
existing public key.


### Create a Key Pair
Click **Create Key Pair** on the right side of the screen. Give it any name
that you would like and select **SSH Key** as the key type. Finally, click
**Create Key Pair**. Your browser will automatically download the private key 
for you.


### Upload a Public Key
Click **Import Public Key** on the right side of the screen. Give it any name
that you would like and select **SSH Key** as the key type. Then either select
the public key file or paste its contents into the text box. Finally,
click **Import Public Key**.


## Adding an SSH Security Group
Before you are able to use your SSH key to authenticate with an instance,
you will need to set up a security group that will allow SSH connections.

Navigate to the **Security Groups** page. You can do this by going to **Project**
-> **Network** -> **Security Groups** in the navigation menu on the left.

![Security group page web view](security_groups.PNG)

Click **Create Security Group** on the right side of the screen. In the popup
window, name the security group "SSH" and then click **Create Security Group**.
Next, click **Add Rule** on the right side of the screen. In the **Rule** 
dropdown, select **SSH**. Click **Add** to add the rule.

## Launching a Development Instance
Development instances on the SDSC Cloud come prepackaged with software for
development.

Navigate to the **Instances** page.
You can do this by going to **Project** -> **Compute** -> **Instances** in the 
navigation menu on the left.

![Instances page web view](instances_page.PNG)

Click **Launch Instance** on the right side of the screen.

![Launch instance page web view](launch_instance.PNG)

In the popup window, give your new instance any name you would like.

![Instance name](instance_name.PNG)

Click on **Source** on the left. In the dropdown for **Select Boot Source**,
select **Image**. Under the **Available** section, select **dev_env_0.0.1**
by clicking on the up arrow at the end of the row.

![Instance source](instance_source.PNG)

Click on **Flavor** on the left. Select the flavor with the CPU and RAM
configuration that meets your needs by clicking on the up arrow at the end
of the row. For this example, I will use **m1.medium**.

![Instance flavor](instance_flavor.PNG)

Click on **Security Groups** on the left. Select the **SSH** security group
that you created earlier by clicking on the up arrow at the end of the row.

![Instance security groups](instance_security_groups.PNG)


Click on **Key Pair** on the left. Select the SSH Key that you created earlier
by clicking on the up arrow at the end of the row.

![Instance key pair](instance_key_pair.PNG)

Click **Launch Instance** on the bottom right of the popup to finish.

### Getting a public IP Address
Your newly created instance will not be able to be reached until you
give it a public IP address by **Associating a Floating IP** with it.
From the instances page, find the instance that you would like to add an
IP to. Click the dropdown arrow at the end of the row and click 
**Associate Floating IP**.

![Associate floating IP](floating_ip.PNG)

In the **IP Address** field, click the + at the end.

![Add floating IP](add_floating_ip.PNG)

In the popup window, click **Allocate IP**. Then click **Associate** in the
bottom right of the popup window.

Your instance should now be accessible at the associated IP address. Note that 
this is the IP address that starts with **132.\*** not **10.\*** .

## Connecting to an Instance
You should be able to connect to your instances using the SSH key that you
selected when created the instance.

For help connecting from Mac or Linux, look [here](https://sdsc-ucsd.atlassian.net/wiki/spaces/SC/pages/110034993/SSH+to+Instance+using+Mac+and+Linux).
For help connecting from Windows, look [here](https://sdsc-ucsd.atlassian.net/wiki/spaces/SC/pages/110034995/SSH+to+Instance+using+Windows).


## Shelving an Instance
Instances should only be kept running when they are being used. When instances
are not in use, they should be _shelved_. Shelved instances are essentially
paused until they are needed again. Data stays on shelved instances and is
not lost.

From the instances page, find the instance that you would like to shelve.
Click the dropdown arrow at the end of the row and click 
**Shelve Instance**.

![Add floating IP](shelve_instance.PNG)

## Unshelving an Instance
From the instances page, find the instance that you would like to unshelve.
Click the dropdown arrow at the end of the row and click 
**Unshelve Instance**.

![Add floating IP](unshelve_instance.PNG)

## More Information and Guides
For more information and guides on how to use the SDSC cloud, see the 
[SDSC Cloud Wiki](https://sdsc-ucsd.atlassian.net/wiki/spaces/SC/overview).