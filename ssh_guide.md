# SSH and Remote Development Guide

This is a short guide for beginners on how to set up a remote connection to a PC on campus. This is often necessary for a few reasons:

-  You may have a GPU-intensive process to run (such as training a neural network) and want to make use of the higher-end GPUs we have in the server room and on the UCT HPC.

-  You want to work from home (or anywhere else) and want to use software or hardware resources you have set up on your lab PC.

-  You want to access data that is stored on the UCT network.

In general it's a very useful tool. This guide will focus on accessing machines on the UCT network, but if you want to access a machine on your own network, the steps are very similar.

## Requirements

On your personal PC/laptop you'll need a couple pieces of software to get started:

-  Cisco AnyConnect VPN - http://www.icts.uct.ac.za/AnyConnect
    This is a Virtual Private Network (VPN) that, when active, will connect your device to the UCT network. This means you can directly see and connect to any IPs present on campus. You can follow the instructions on the given link to set it up (you'll need your UCT account login details!)

-  An SSH client such as OpenSSH - https://www.openssh.com/
    The exact client you install may vary depending on your OS/preferences, but you'll need an SSH package to use or host an SSH connection. Most terminal environments come with one pre-installed.

In addition to this, you'll want to make sure you have a user account on the host machine. If you don't have one already you'll need to contact a system administrator about it.

## New User

A newcomer needs to make an new user account on the server.
Please tell your desired **username** and **password** to admin users:
- Gerald Maswoswere (`nyemwero`)
- Zico Da Silva (`zico`)
- Amaan Vally (`amaan`)
- Naoya Muramatsu (`naoya`)
- Michael Katsoulis (`ktsmic005`)

To the admin user: this is the commands to add a new user.
```bash
$ sudo adduser -m [newusername]
$ sudo passwd [newusername]
```

## Connecting to a Lab PC

To establish an SSH connection, there are a few simple steps to follow:

1.  Launch Cisco AnyConnect and connect to the address vpn.uct.ac.za - you'll need to log in with your UCT account.

2.  Once the VPN connection is active, open a terminal window and type the command:

    `ssh user@machine-address.uct.ac.za`

    This will open an SSH connection to the machine on the network denoted by `machine-address.uct.ac.za` and log you in with the username `user`. You will then need to type your password.

    For example, if I want to log in to the i9 machine we have set up in the server room, I would type:

    `ssh daniel@mechatronics-monster1.uct.ac.za`

    ... as we have given the address `mechatronics-monster1.uct.ac.za` to that machine.

3.  That's it! Once you have logged in your terminal should show you connected to your host at the /home/ directory.

## Useful Terminal Commands

The vast majority of the machines that you connect to on the UCT network will be running on some distribution of Linux - there are lots of reasons for this that we won't get into here. It always pays to be familiar with Linux terminal commands. There are plenty of guides and tutorials on the internet for you to learn the Linux terminal if you don't already know the basic commands.

Aside from the basic filesystem commands such as `cd` and whatnot, there are a few specific commands that will help you hugely for remote development:

-   scp

    You may recognise this command as the stock-standard "copy-paste" command for the Linux terminal. You can also use this command to copy files securely from machine to machine over an SSH connection.

    Let's say I want to copy the file "image.png" from my /home/daniel directory on the i9 machine to my desktop on my local machine. The command I would run would be:

    `scp daniel@mechatronics-monster1.uct.ac.za://home/daniel/image.png /home/daniel/Desktop/`

    It will prompt you for a password and then will begin copying the file over. If you want to copy an entire folder, you can use `scp -r`.

-   tmux

    Tmux is a terminal multiplexer. This means that you can essentially open a new terminal session on top of the one you are already in. Any commands you run in this terminal session will run independently of the commands you run in any other session or window. And, most importantly, the command you ran in a tmux session will *keep running* after you log out, lose connection or close the window.

    This is helpful if you need to run a command that takes a long time to execute such as training a network.

    To open a tmux session you simply type `tmux`. Once you have your commands running, you need to use `ctrl+b d` to detach from the session. Once you have returned and logged back in, you can type `tmux attach` to reattach to that session and check on your commands/processes.

-   nvidia-smi

    This is part of the NVidia utils package and will show you some information about whichever GPUs are installed in your system. It shows temperature, total memory capacity, used memory, and the exact model of each GPU. The other useful thing you will see in this screen is what processes are running on your GPUs and how much memory they are using. This is nice if you want to confirm that your training is running on the GPUs, and you can keep track of how much memory it is using.

-   nano

    This is a very basic text editor that runs in a terminal window. To edit a file you can type `nano file.txt`. The commands you can use inside nano will be shown on-screen, but in case you get stuck, you can use `ctrl+x` to exit nano.

    If you find you are editing text a lot in the terminal, you may want to switch to a more advanced text editor such as vim or emacs.

## VS Code

If you are writing a lot of code that is being hosted on a remote machine, you probably don't want to keep having to use nano or vim to write your code. Luckily, VS Code has a pretty well fleshed out remote development extension. This will allow you to open a SSH connection to your remote host (as long as you are connected to the VPN!) and use VS Code to edit any text/code that you need to, with the added benefits of syntax highlighting as well as all your other VS Code extensions.

Simply go to the extensions tab in VS Code and install the "Remote Development" extension. Once you have it installed, you can open up the VS Code command pallet, search "remote," and select the "Remote-SSH: Connect to a Host" command. Here you can type in your ssh command as per normal and voila, you are connected remotely.

## Setting Up Your Own Machine as a Remote Host

#TODO if people are interested
