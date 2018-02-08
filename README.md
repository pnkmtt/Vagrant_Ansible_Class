# Vagrant_Ansible_Class
Basic class on Ansible using Vagrant and Virtualbox

<h1>Introduction</h1>

<p>Vagrant designed to run through multiple platforms including currently Mac OS X, Microsoft Windows, Debian, Ubuntu, CentOS, RedHat and Fedora, in this document we will handle how to configure and run virtual development environment through Vagrant from scratch to up and running, on Windows environments.</p>

<p> VirtualBox is an Oracle product that allows you to run virtual guests on your machine for development.  Vagrant understands how to call VirtualBox to create an instance on a private network, behind a NAT, on your machine so you can easily do development </p>


<h1>Installing the Development Windows Environment</h1>

<p>To install our environment we should follow the below sections in order</p>

<p>Installing Vagrant</p>

<p>Installing Git </p>

<p>Installing Virtualbox</p>

<p>Installing Putty</p>


<h2>Installing Vagrant</h2>

<p>First thing, you need to download vagrant setup from <a href="http://www.vagrantup.com/downloads.html">http://www.vagrantup.com/downloads.html</a>, and then run it.</p>

<p>Setup wizard is straightforward, just it will ask to accept license agreement and the path to install, as you will need to use command line, please choose short path as you can, for example in our case, we will use “D:\Vagrant”, it might ask you to restart at the end of setup.</p>

<p>The setup here is some longer but if you just click “Next” without any changes, it will be fine.</p>

<h2>Installing Git</h2>

<p>Download Git command line setup from <a href="https://github.com/git-for-windows/git/releases">https://github.com/git-for-windows/git/releases</a>, and then run it.</p>

<p> Alternative <a href="https://git-scm.com/download/win">https://git-scm.com/download/win</a> </p>

<p>You may need to update your path so that you can find git on the command line</p>

<p>On windows 10 go to this url for help:  <a href="https://www.java.com/en/download/help/path.xml">https://www.java.com/en/download/help/path.xml</a></p>

<h2>Installing VirtualBox</h2>

<p>You need now to download VirtualBox, use the following link to download the latest release of VirtualBox <a href="https://www.virtualbox.org/wiki/Downloads">https://www.virtualbox.org/wiki/Downloads</a></p>

<p>The setup here is some longer but if you just click “Next” without any changes, it will be fine.</p>

<h2>Installing Putty</h2>

<p>You need now to download Putty, use the following link to download the latest release of Putty <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html</a></p>

<h1> Creating your Vagrant VM</h1>

<p>Now that we have everything installed we need to download the required Vagrant files</p>

<p>From a new directory and on the command line run this command: 'git clone https://github.com/pnkmtt/Vagrant_Ansible_Class'</p>

<p>This will download the Vagrant file and allow us to create your new VirtualBox VM</p>

<p>Once the clone has completed, 'cd' to the target directory</p>

<p>We will now create our VM, run the command 'vagrant up' compare to the output below</p>

<p>You may have to approve the creation of a network adapter on your system say yes to any questions, this does not compromise your OS in any way</p>

Example output from 'vagrant up'

```
C:\Users\panik\Dropbox\git\Vagrant_Ansible_Class>Bringing machine 'default' up with 'virtualbox' provider...
==> default: Box 'v0rtex/xenial64-iso' could not be found. Attempting to find and install...
    default: Box Provider: virtualbox
    default: Box Version: >= 0
==> default: Loading metadata for box 'v0rtex/xenial64-iso'
    default: URL: https://vagrantcloud.com/v0rtex/xenial64-iso
==> default: Adding box 'v0rtex/xenial64-iso' (v20180126.0.0) for provider: virtualbox
    default: Downloading: https://vagrantcloud.com/v0rtex/boxes/xenial64-iso/versions/20180126.0.0/providers/virtualbox.box
    default:
==> default: Successfully added box 'v0rtex/xenial64-iso' (v20180126.0.0) for 'virtualbox'!
==> default: Importing base box 'v0rtex/xenial64-iso'...
==> default: Matching MAC address for NAT networking...
==> default: Checking if box 'v0rtex/xenial64-iso' is up to date...
==> default: Setting the name of the VM: Vagrant_Ansible_Class_default_1518127578490_62760
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
    default: Adapter 2: hostonly
==> default: Forwarding ports...
    default: 22 (guest) => 2222 (host) (adapter 1)
==> default: Running 'pre-boot' VM customizations...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
    default: Warning: Connection reset. Retrying...
    default: Warning: Connection aborted. Retrying...
    default: Warning: Remote connection disconnect. Retrying...
    default: Warning: Connection aborted. Retrying...
    default: Warning: Connection reset. Retrying...
    default: Warning: Connection aborted. Retrying...
    default:
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default:
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if it's present...
    default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
==> default: Setting hostname...
==> default: Configuring and enabling network interfaces...
==> default: Mounting shared folders...
    default: /vagrant => C:/Users/panik/Dropbox/git/Vagrant_Ansible_Class

```

<h1> Accessing your new VirtualBox based VM </h1>

<p>  Using putty access 127.0.0.1:2222, the user is vagrant, the password is vagrant.

<h1>Installing Ansible on your new VM</h1>

<p>We need to have ansible installed on our new host run the following commands to install Ansible and its dependicies</p>

```
#sudo apt-get update
#sudo apt-get install software-properties-common
#sudo apt-get install python-software-properties
#sudo apt-get install build-essential libssl-dev libffi-dev python-dev
#sudo apt-add-repository ppa:ansible/ansible
#sudo apt-get update

#sudo apt-get install ansible
#

<h1>Clean up your Vagrant install</h1>

<p>When you are ready to finish the exercise you should remove your VM</p>

<p>In order to do this run the follow command from the original directory 'vagrant destroy'  you will have to answer 'y' to complete the destruction</p>

```
C:\Users\panik\Dropbox\git\Vagrant_Ansible_Class>vagrant destroy
    default: Are you sure you want to destroy the 'default' VM? [y/N] y
==> default: Forcing shutdown of VM...
==> default: Destroying VM and associated drives...

```


