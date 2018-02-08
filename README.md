# Vagrant_Ansible_Class
Basic class on Ansible useing Vagrant and Virtualbox

<h1>Introduction</h1>

<p>Vagrant designed to run through multiple platforms including currently Mac OS X, Microsoft Windows, Debian, Ubuntu, CentOS, RedHat and Fedora, in this document we will handle how to configure and run virtual development environment through Vagrant from scratch to up and running, on Windows environments.</p>

<p> VirtualBox is an Oracle product that allows you to run virtual guests on your machine for development.  Vagrant understands how to call VirtualBox to create an instance on a private network, behind a NAT, on your machine so you can eaisly do development </p>


<h1>Installing the Development Windows Environment</h1>

<p>To install our envriuoment we should follow the below sections in order</p>

<p>Installing Vagrant</p>

<p>Installing Git </p>

<p>Installing Virtualbox</p>

<p>Installing Putty</p>


<h2>Installing Vagrant</h2>

<p>First thing, you need to download vagrant setup from <a href="http://www.vagrantup.com/downloads.html">http://www.vagrantup.com/downloads.html</a>, and then run it.</p>

<p>Setup wizard is straightforward, just it will ask to accept license agreement and the path to install, as you will need to use command line, please choose short path as you can, for example in our case, we will use “D:\Vagrant”, it might ask you to restart at the end of setup.</p>

<p>The setup here is some longer but if you just click “Next” without any changes, it will be fine.</p>

<h2>Installing Git</h2>

<p>Download Git commandline setup from <a href="https://github.com/git-for-windows/git/releases">https://github.com/git-for-windows/git/releases</a>, and then run it.</p>

<p> Alernative <a href="https://git-scm.com/download/win">https://git-scm.com/download/win</a> </p>

<p>You may need to update your path so that you can find git on the commandline</p>

<p>On windows 10 go to this url for help:  <a href="https://www.java.com/en/download/help/path.xml">https://www.java.com/en/download/help/path.xml</a></p>

<h2>Installing VirtualBox</h2>

<p>You need now to download VirtualBox, use the following link to download the latest release of VirtualBox <a href="https://www.virtualbox.org/wiki/Downloads">https://www.virtualbox.org/wiki/Downloads</a></p>

<p>The setup here is some longer but if you just click “Next” without any changes, it will be fine.</p>

<h2>Installing Putty</h2>

<p>You need now to download Putty, use the following link to download the latest release of Putty <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html</a></p>

<h1> Creating your Vagrant VM</h1>

<p>Now that we have everyting installed we need to download the required Vagrant files</p>

<p>From a new directory and on the command line run this command: git clone https://github.com/pnkmtt/Vagrant_Ansible_Class</p>

<p>This will download the Vagrant file and allow us to create your new VirtualBox VM</p>

<h1> Accessing your new VirtualBox based VM </h1>

<p>  Using putty access 127.0.0.1:2222, the user is vagrant, the password is vagrant.



