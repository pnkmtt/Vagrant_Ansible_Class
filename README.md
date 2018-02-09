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

<h2>Download the class material via git</h2>

<p>From a new or exsisting directory i.e c:/Users/Panik/Downloads and on the command line run this command: 'git clone https://github.com/pnkmtt/Vagrant_Ansible_Class'</p>

<p>This will download the Vagrant file and allow us to create your new VirtualBox VM in a directory called Vagrant_Ansible_Class</p>

<p>Once the clone has completed, 'cd' to the target directory, For example cd c:/User/panik/Downloads/Vagrant_Ansible_Class</p>

<p>We will now create our VM based on the downloaded files, run the command 'vagrant up' compare to the output below</p>

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

<h2> Accessing your new VirtualBox based VM </h2>

<p>  Now that the instances is up ssh into the VM via putty.  The host information is 127.0.0.1 and the port is 2222, the user is vagrant, the password is vagrant. </p>

<h2>Installing Ansible on your new VM</h2>

<p>We npw need to install ansible on our new host.  Run the following set of commands to install Ansible and its dependicies. I did not automate this process to show the package install process </p>

```
sudo apt-get update -y
sudo apt-get install software-properties-common -y
sudo apt-get install python-software-properties -y
sudo apt-add-repository ppa:ansible/ansible -y
sudo apt-get update
sudo apt-get install ansible -y
```

<p>To make sure ansible is installed run 'ansible --version'</p>

```
vagrant@myxenial64:/vagrant$ ansible --version
ansible 2.0.0.2
  config file = /etc/ansible/ansible.cfg
  configured module search path = Default w/o overrides
```

<p>We now have a working ansible install</p>

<h2>Running our first ansible playbook</h2>

<p>Ansible as a configuration tool uses ssh to access the hosts that it configures.  Since we are doing this on the newly created VM, we will be sshing to the localhost and configuring our applications.</p>

<p>In order to this we need to take a setp to generate an sshkey for the vagrant user and put it in the authorized_keys file. The below example shows the creation of an RSA ssh key and the population of the vagrant user authorized_keys file.</p>

<p>As the vagrant user run 'ssh-keygen -t rsa' and accept the defaults.  Once complete copy the newly generated RSA public key into the vagrant users authorized_keys file. Run the command 'cat .ssh/id_rsa.pub > .ssh/authorized_keys'  Note: this is not how you would manage the key files in production, but we are using sudo which is perfered over direct root access</p>

<p>To test the connection ssh to the localhost and you will not need a password 'ssh localhos'.  Exit once you have confirmed access.</p>

```
vagrant@myxenial64:~$ ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/home/vagrant/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/vagrant/.ssh/id_rsa.
Your public key has been saved in /home/vagrant/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:XiBndxIcOQxuaBzyhJoNbi6Bbb7UdD9bBHnMec7FNiQ vagrant@myxenial64
The key's randomart image is:
+---[RSA 2048]----+
|    ..o .Bo+Eo.  |
|  . .= +o X...=  |
|.o =  * *oo=.o . |
|o B o..= o.oo    |
| * o . .S..      |
|. + .  .o..      |
| o .    .+       |
|  .     .        |
|                 |
+----[SHA256]-----+
vagrant@myxenial64:~$ cat .ssh/id_rsa.pub > .ssh/authorized_keys
vagrant@myxenial64:~$ ssh localhost
The authenticity of host 'localhost (::1)' can't be established.
ECDSA key fingerprint is SHA256:7AfUe0N0zVc8EFUtFyzW7f9NlVztFFAdXg9T37N4L8c.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'localhost' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 16.04.3 LTS (GNU/Linux 4.4.0-112-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
Last login: Fri Feb  9 18:26:40 2018 from 10.0.2.2
vagrant@myxenial64:~$ exit
logout
Connection to localhost closed.
```

<h2>Accessing our Ansible Files</h2>

<p>The VM has mounted your working directy as a partition it can acess.  This can be found under /vagrant.  Run 'cd /vagrant' to enter this directory</p>

<p>In this directory you will fine several files that allow ansible to configure a host for apache, mariaDB, and populates configuration files to allow apache to store and access data within the database.</p>

```
hosts - lists all ansible hosts and configuration parameters such as ssh keys

playbook.yml - base ansible playbook that details what roles to install on specific hosts, in our case the list is 'all'

roles - directory that holds application definitions

roles\apache2 - top level of the apache2 role

roles\apache2\tasks - contains yml files that tell ansible what action to take

roles\apache\files - contains files that can be copied to the remote hosts

roles\mariadb\tasks - contains yml files that tell ansible what action to take

roles\mariadb\files - contains files that can be copied to the remote hosts

```

<p>To have ansible install apache and mariadb run this command 'ansible-playbook -i hosts playbook.yml --sudo' you will have to accept the ssh key on first access.</p>

<p>Pay attention to the output and you will see each step being taken to confiugre the applications, insert data, and allow apache to access mariadb.</p>

<p>Once the playbook is complete in your local browser put in the url http://localhost:8888/db.php.  The response comes from the backend mariadb</p>

<h1>Clean up your Vagrant install</h1>

<p>When you are ready to finish the exercise you should remove your VM</p>

<p>In order to do this run the follow command from the original directory 'vagrant destroy'  you will have to answer 'y' to complete the destruction</p>

```
C:\Users\panik\Dropbox\git\Vagrant_Ansible_Class>vagrant destroy
    default: Are you sure you want to destroy the 'default' VM? [y/N] y
==> default: Forcing shutdown of VM...
==> default: Destroying VM and associated drives...
```


