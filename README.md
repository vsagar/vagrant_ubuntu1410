### Plain vagrant setup for ubuntu 14.10

This is a plain Ubuntu 14.10 VM setup using [vagrant](https://www.virtualbox.org) which sets up a [headless version](http://whatis.techtarget.com/definition/headless-system) of Operating system on our system. This setup required some installations for running the file


#### Install Necessary Dependencies

- [Install Virtual Box ](https://www.virtualbox.org/wiki/Downloads)
- [Install Vagrant ](http://www.vagrantup.com/downloads.html)
- Install comand line interface with ssh enables: [cygwin] (http://www.howtogeek.com/howto/41560/how-to-get-ssh-command-line-access-to-windows-7-using-cygwin/) or powershell in Windows for accessing the vagrant machine 

#### Checking Installation 

After these are installed, if the installations have been correctly installed, on running ```vagrant -v``` this will give us the version printed on the console and Vagrant is now successfully installed on your system. 

The Vagrant installer should automatically add Vagrant to your system’s PATH.

#### Running the setup

Navigate to the folder you want your project to be at in your terminal and do:

```git clone https://github.com/vsagar/vagrant_ubuntu1410.git```

 
Next, navigate to the folder and start vagrant:

```
cd vagrant_ubuntu1410
vagrant up
```

At this point Vagrant will start building a virtual environment based on the configuration file called “Vagrantfile”. If it finishes without any errors ssh into the server as, its a ``sudo access``` username.

```
vagrant ssh
```

#### Vagrant Commands

There’s a ton of commands you can use to talk to Vagrant. For a full list see the official docs here, but I’ll go over the more common ones.

```vagrant up```

vagrant up This is the command you just ran to boot the box up and provision the server based on the configuration file Vagrantfile. I use this for starting as well as resuming my environments.

```vagrant suspend```

vagrant suspend Use this command to “pause” your virtual environment. Make sure you do this before shutting down your computer to safely be able to restore the environment later.

Starting, Pausing, and Resuming: To start or restore the environment you can just run vagrant up. The state will be saved and everything should be where you left it off from including your database changes.
```vagrant destroy```

vagrant destroy This permanently removes the virtual environment from your machine.

```vagrant reload```

vagrant reload and vagrant reload --provision If your environment suddenly stops working, it’s useful to reboot by running this command. If you add the --provision flag, it will reprovision the box as well. This is useful with removing or adding things to the server via Cookbooks or Puppet.

```vagrant ssh```

vagrant ssh Anything you edit on your computer in the public folder is automatically shared to the virtual environment without having to SSH in. However, if for whatever reason you need to connect to the virtual server, just run this command.

```vagrant ssh-config```

vagrant ssh-config This lets you see the detailed login credentials of how you could connect to the virtual environment.
