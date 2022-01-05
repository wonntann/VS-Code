This repo will take you through the steps to setup SSH remote access for your local machines, as well as, on VS Code without having to keep working in the terminal.


<!--  SHIELDS  -->
![GitHub](https://img.shields.io/github/license/wonntann/vs-code?color=informational&logoColor=yellow&style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/wonntann/vs-code?color=red&style=for-the-badge)
![GitHub Issues](https://img.shields.io/github/issues-raw/wonntann/vs-code?color=critical&style=for-the-badge)



<!--  TABLE OF CONTENTS  -->
<details>
    <summary>Table of Contents</summary>
    <ol>
        <li><a href="#how-to-read-this-project">How To Read This Project
        <ul>
            <li><a href="#prerequisites">Prerequisites</a></li>
            <li><a href="#installation">Installation</a></li>
        </ul>
        </li>
        <li><a href="#how-git-works">How Git Works</a></li>
        <li><a href="#git-started">Git Started</a>
            <ul>
                <li><a href="#markdown-lesson">Markdown Lesson</a></li>
                <li><a href="#uploading-your-project-to-github">Uploading your project to GitHub</a></li>
                <li><a href="#managing-conflicts">Managing Conflicts</a></li>
                <li><a href="#github-pages">GitHub Pages</a></li>
                <li><a href="#collaboration">Collaboration</a></li>
            </ul>
        </li>
        <li><a href="#contributing">Contributing</a>
        <ul>
            <li><a href="#license">License</a></li>
            <li><a href="#contact">Contact</a></li>
            <li><a href="#resources">Resources</a></li>
        </ul>
        </li>
    </ol>
</details>
</br>
</br>
</br>

# Extension Used In This Repository
- [Remote Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)

# What is SSH?
SSH, secure shell protocol, allows access to a remote machine (i.e. computer, virtual machine...). SSH allows you to access an app on a different computer, giving you the ability to view, modify, run and/or debug the files located on the connected device.

# Common Uses
Schools
    - SSH into lab machines to access that machine's dependencies required for an assignment, without needing that sepcific operating system.

Home
    - Want to access information/documents on another computer already setup with SSH. Allows you to transfer files over SSH over using a USB, the cloud, or any other external device.

# Microsoft Exercise
- [Remote Development over SSH](https://code.visualstudio.com/docs/remote/ssh-tutorial) tutorial from the Microsoft Official website using AWS to serve as a client.


# How To Read This
Below are the steps that I took in order to connect via VS Code over SSH on the same network with two different machines.

# Learning Objectives
- First exercise will connect two remote machines via SSH
- Second exercise will open the files on the remote machine in VS Code via the remote extension

# Terminology
- SSH
- Client/Computer2
- Server/Remote host
- Hostname
- IP address
- Terminal/Command Line/Bash

# What you need
- Computer username (name used to login)
- Hostname (can be IP address computer is connected to)
    - On Linux, to find the ip address, **enter** **ip add** into the terminal
    ``` bash
    ~$ ip add
    ```
    Look at the **2: eno1: inet** ip address
- Two machines with met requirements from below

<div id="requirements"></div>
# Requirements for two machines on the same network
    - On client machine: Install [OpenSSH compatible SSH client](https://code.visualstudio.com/docs/remote/troubleshooting#_installing-a-supported-ssh-client)
    - On server machine: Install [OpenSSH compatible SSH server](https://code.visualstudio.com/docs/remote/troubleshooting#_installing-a-supported-ssh-server)
    - Install [Visual Studio Code](https://code.visualstudio.com/)
    - Install [Remote Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)

# How To Connect Your Machine
## Exercise 1: Connecting Two Local Machines via SSH
1. Setup SSH host
    - Iinstall the ssh openssh on the server (machine #1 that is hosting information and connecting to the other machine)
- On Linux:
    ``` bash
    sudo apt-get install openssh-server
    ```
- On Windows: [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

- On Mac: Comes pre-installed

2. Connect to a remote host/computer2
    - Enter the following command in the client terminal, making sure to replace the username with the host machine's \<username> and the \<hostname> with the ip address for that host machine.
    ``` bash
    ssh <username>@<hostname>
    ```
3. Once your terminal connects to the host machine, the username and hostname will be in the terminal. You can access all of the files via the terminal and edit the files via Vim, nano or transfer it to the device.

Next, I will take you through the steps to SSH into the host machine via VS Code.

## Exercise 2: Working in VS Code
VS Code permits connection over SSH into another machine using VS Code to interact with files and folders on the remote filesystem. Connecting to the separate machine through VS Code, allows you to access any tools or dependencies pre-installed on that remote machine.

Now that you have connected via SSH you can connect straight through the VS Code extension. If you didn't follow the SSH, you can still accomplish the connection via VS Code, as long as the <a href="#requirements">requirements</a> are met.

## Steps
1. Open VS Code, and open the remote SSH-Open SSH Host by clicking ![extension](/assets/extension.png) and ** Connect to host ** or connect to your host that you just set up.
2. If your hostname is not in the dropdown selection, type your user and hostname then hit **enter**
3. If prompted, enter you host password
4. Navigate to **Open Folder** or hit **CTRL** + **o** to start accessing the files on the host.