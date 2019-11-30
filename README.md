# sshuttle-poor-mans-vpn
vpn-over-ssh

Do you ever wanted to use SSH as a VPN? There is little piece of useful utility called “sshuttle” is available to completely turn your SSH connection as VPN. sshuttle is a transparent proxy server that works as a poor man’s VPN over ssh. You don’t need any admin account on your remote system. It supports DNS tunneling and works with Linux and MacOS platforms.

There are so many free and commercial VPN providers available. But that VPN’s can be hassle and risky and it may lead you to much trouble. But sshuttle is the simplest, but powerful way to setup VPN on any network to which you have SSH access. The beauty of this application is you need root access in your local system, but don’t need any administrative access on your remote side. Cool, isn’t it?

It is possible to run more than one VPN connection from a single local system to connect to different remote systems every time as long as they have python 2.3 or higher. All modern Unix/Linux systems comes with python installed. If your remote system doesn’t have python, it’s not that difficult to install python. sshuttle will automatically upload and run its source code to the remote python interpreter.

Whenever you launch sshuttle as root user , it will  modify your system firewall to tunnel all traffic through a remote SSH connection and you don’t need a root access on your remote client. So you don’t have to worry about security whether you’re trying to access the remote server from a coffee shop, hotel or net-cafe.

Installation

On Debian/Ubuntu and its derivatives:

Just enter the following command to install sshuttle.

$ sudo apt-get install sshuttle
On RHEL and its derivatives:

Add EPEL repository as show in the following link.

– Install EPEL Repository On RHEL / CentOS / Scientific Linux 6

Then run the following command to install it.

# yum install sshuttle
Configuration

You don’t need to configure anything either on local or remote side. Just install python on your remote system if it doesn’t has.

Usage

Connecting to remote systems using sshuttle is fairly simple and straight forward.

From your local system Terminal, enter command:

# sshuttle -r username@sshserver 0.0.0.0/0 -vv
Or

$ sudo sshuttle -r username@sshserver 0.0.0.0/0 -vv
Or

$ sudo sshuttle -r username@sshserver 0/0 -vv
If you would also like your DNS queries to be proxied through the DNS server of the server you are connect to, then connect as shown below.

# sshuttle --dns -vvr username@sshserver 0/0
Or

$ sudo sshuttle --dns -vvr username@sshserver 0/0
You will be may be prompted for one or more passwords; first, the local password to become root using either sudo or su, and then the remote ssh password.

That’s it. Now you’ll be able to access your remote clients.

official github page:
https://github.com/apenwarr/sshuttle
