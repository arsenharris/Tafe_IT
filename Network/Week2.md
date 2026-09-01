# Basic Switch and End Device Configuration
Explain how to access a Cisco IOS device for configuration purposes.
Explain how to navigate Cisco IOS to configure network devices.
Describe the command structure of Cisco IOS software.
Configure a Cisco IOS device using CLI.
Use IOS commands to save the running configuration.
Explain how devices communicate across network media.
Configure a host device with an IP address.
Verify connectivity between two end devices.

### 2.1 Cisco IOS Access
##### 2.1.1 Operating Systems
All end devices and network devices require an operating system (OS).  The portion of the OS that interacts directly with computer hardware is known as the kernel. The portion that interfaces with applications and the user is known as the shell. The user can interact with the sheil using a command-line interface (CLI) or a graphical user interface (GUI).
*   Shell - The user interface that allows users to request specific tasks from the computer. These requests can be either through the CLI or GUl interfaces.
*   Kernel - Communicates between the hardware and software of a computer and manages how hardware resour used to meet software requirements.
*   Hardware - The physical part of a computer including underlying electronics.

When using a CLI, the user interacts directly with the system in a text-based environment by entering commands on the keyboard at a command prompt. The system executes the command, often providing textual output. The CLI requires very little overhead to operate. However, it does require that the user have knowledge of the underlying command structure that controls the system. 
##### 2.1.2 GUI
A GUI such as Windows, macOS, Linux KDE, Apple iOS, or Android allows the user to interact with the system using an environment of graphical icons, menus, and windows. The GUl example in the figure is more user-friendly and requires less knowledge of the underlying command structure that controls the system. For this reason, most users rely on GUI environments.

However, GUls may not always be able to provide all the features available with the CLI. GUls can also fail, crash, or simply not operate as specified. For these reasons, network devices are typically accessed through a CLI. The CLI is less resource intensive and very stable when compared to a GUI.
The family of network operating systems used on many Cisco devices is called the Cisco Internetwork Operating System (IOS). Cisco IOS is used on many Cisco routers and switches regardless of the type or size of the device.
Each device router or switch type uses a different version of Cisco IOS. Other Cisco operating systems include IOS XE, IOS XR, and NX-OS.
Note: The operating system on home routers is usually called firmware. The most common method for configuring a home router is by using a web browser-based GUI.
##### 2.1.3 Purpose of an OS
Network operating systems are similar to a PC operating system. Through a GUI, a PC operating system enables a user to do the following:
*   Use a mouse to make selections and run programs
*   Enter text and text-based commands
*   View output on a monitor
A CLI-based network operating system (e.g., the Cisco IOS on a switch or router) enables a network technician to do the following:
*   Use a keyboard to run CLI-based network programs
*   Use a keyboard to enter text and text-based commands
*   View output on a monitor
Cisco networking devices run particular versions of the Cisco IOS. The IOS version is dependent on the type of device being used and the required features. While all devices come with a default IOS and feature set, it is possible to upgrade the IOS version or feature set to obtain additional capabilities.
##### 2.1.4 Access Methods
A switch will forward traffic by default and does not need to be explicitly configured to operate. For example, two configured hosts connected to the same new switch would be able to communicate.
Regardless of the default behavior of a new switch, all switches should be configured and secured.
Console
This is a physical management port that provides out-of-band access to a Cisco device. Out-of-band access refers to access via a dedicated management channel that is used for device maintenance purposes only. The advantage of using a console port is that the device is accessible even if no networking services are configured, such as performing the initial configuration. A computer running terminal emulation software and a special console cable to connect to the device are required for a console connection.
Secure Shell(SSH)
SSH is an in-band and recommended method for remotely establishing a secure CLI connection, through a virtual interface, over a network. Unlike a console connection, SSH connections require active networking services on the device, ilksluding an active interface configured with an address. Most versions of Cisco IOS include an SSH server and an SSH client that can be used to establish SSH sessions with other devices.
Telnet
Telnet is an insecure, in-band method of remotely establishing a CLI session, through a virtual interface, over a network. Unlike SSH, Telnet does not provide a secure, encrypted connection and should only be used in a lab environment. User authentication, passwords, and commands are sent over the network in plaintext. The best practice is to use SSH instead of Telnet. Cisco IOS includes both a Telnet server and Telnet client.
Note: Some devices, such as routers, may also support a legacy auxiliary port that was used to establish a CLI session remotely over a telephone connection using a modem. Similar to a console connection, the AUX port is out-of-band and does not require networking services to be configured or available.
There are several terminal emulation programs you can use to connect to a networking device either by a serial connection over a console port, or by an SSH/Telnet connection. These programs allow you to enhance your productivity by adjusting window sizes, changing font sizes, and changing color schemes.

##### 2.1.5 Terminal Emulation Programs
There are several terminal emulation programs you can use to connect to a networking device either by a serial connection over a console port, or by an SSH/Telnet connection. These programs allow you to enhance your productivity by adjusting window sizes, changing font sizes, and changing color schemes.

Putty, Tera Term, Secure CRT
###### Quiz: 
Which access method would be most appropriate if you were in the equipment room with a new switch that needs to be configured?
Console, Telnet/SSH,Aux

Which access method would be most appropriate if your manager gave you a special cable and told you to use it to configure the switch?
Console, Telnet/SSH,Aux

Which access method would be the most appropriate in-band access to the IOS over a network connection?
Console, Telnet/SSH,Aux

Which access method would be the most appropriate if you call your manager to tell him you cannot access your router in another city over the internet and he provides you with the information to access the router through a telephone connection?
Console, Telnet/SSH,Aux


### 2.1 IOS Navigation
Using the CLI may provide the network administrator with more precise control and flexibility than using the GUI. This topic discusses using CLI to navigate the Cisco IOS.
As a security feature, the Cisco IOS software separates management access into the following two command modes:
*   User EXEC Mode - This mode has limited capabilities but is useful for basic operations. It allows only a limited number of basic monitoring commands but does not allow the execution of any commands that might change the configuration of the device. The user EXEC mode is identified by the CLI prompt that ends with the > symbol.
*   Privileged EXEC Mode - To execute configuration commands, a network administrator must access privileged EXEC mode. Higher configuration modes, like global configuration mode, can only be reached from privileged EXEC mode. The privileged EXEC mode can be identified by the prompt ending with the # symbol.

To configure the device, the user must enter global configuration mode, which is commonly called global config mode.
From global config mode, CLI configuration changes are made that affect the operation of the device as a whole.
Global configuration mode is identified by a prompt that ends with (config)# after the device name, such as Switch(config)#.
Global configuration mode is accessed before other specific configuration modes. From global config mode, the user can enter different subconfiguration modes. Each of these modes allows the configuration of a particular part or function of the IOS device. Two common subconfiguration modes include:
*   Line Configuration Mode - Used to configure console, SSH, Telnet, or AUX access.
*   Interface Configuration Mode - Used to configure a switch port or router network interface.
When the CLI is used, the mode is identified by the command-line prompt that is unique to that mode. By default, every prompt begins with the device name. Following the name, the remainder of the prompt indicates the mode.
For example, the default prompt for line configuration mode is Switch(config-line)# and the default prompt for interface configuration mode is Switch(config-if)#.



Various commands are used to move in and out of command prompts. To move from user EXEC mode to privileged EXEC mode, use the enable command. Use the disable privileged EXEC mode command to return to user EXEC mode.
Note: Privileged EXEC mode is sometimes called enable mode.

*From User exec to priv exec type enable. 
```bash
Switch> enable
Switch#
```
command disable to go back to user exec mode. 
```bash
Switch# disable
Switch>
```


To move in and out of global configuration mode, use the configure terminal privileged EXEC mode command. To return to the privileged EXEC mode, enter the exit global config mode command

```bash
Switch# configure terminal
Switch(config)#
```

```bash
Switch(config)# cexit
Switch#
```


There are many different subconfiguration modes. For example, to enter line subconfiguration mode, you use the line command followed by the management line type and number you wish to access. Use the exit command to exit a subconfiguration mode and return to global configuration mode.

```bash
Switch(config)# line console 0
Switch(config-line)# exit
Switch(config)# 
```

```bash
Switch(config)# exit
Switch#
```


To move from any subconfiguration mode of the global configuration mode to the mode one step above it in the hierarchy of modes, enter the exit command
To move from any subconfiguration mode to the privileged EXEC mode, enter the `end` command or enter the key combination **Ctrl+Z**.

```bash
Switch(config-line)# end
Switch# 
```


You can also move directly from one subconfiguration mode to another. Notice how after selecting an interface, the command prompt changes from (config-line)# to (config-if).

```bash
Switch(config-line)# interface FastEthernet 0/1
Switch(config-if)
```


- **enable**
- **disable**
- **configure terminal( config t)**
- **exit**
- **line console 0**
- **interface vlan 1**
- **end ( ctrl Z)**

When you are learning how to modify device configurations, you might want to start in a safe, non-production environment before trying it on real equipment. NetAcad gives you different simulation tools to help build your configuration and troubleshooting skills. Because these are simulation tools, they typically do not have all the functionality of real equipment. One such tool is the Syntax Checker. In each Syntax Checker, you are given a set of instructions to enter a specific set of commands. You cannot progress in Syntax Checker unless the exact and full command is entered as specified. More advanced simulation tools, such as Packet Tracer, let you enter abbreviated commands, much as you would do on real equipment.

###### Quiz: 

Which IOS mode allows access to all commands and features?
A:privilieged Exec mode 

Which IOS mode are you in if the Switch(config)# prompt is displayed?
A:Global Config

Which IOS mode are you in if the Switch> prompt is displayed?
user exec

Which two commands would return you to the privileged EXEC prompt regardless of the configuration mode you are in? (Choose two.)
end or ctrl Z

### 2.3 The command Structure

This topic covers the basic structure of commands for the Cisco IOS. A network administrator must know the basic IOS command structure to be able to use the CLI for device configuration.
A Cisco IOS device supports many commands. Each IOS command has a specific format, or syntax, and can only be executed in the appropriate mode.
```bash
Switch> show ip protocols
```
- Switch: Promt
- show: Command
- ip protocols: keyword

```bash
Switch> ping 192.168.10.5
```
- Switch: Promt
- ping: Command
- 192.168.10.5: argument

After entering each complete command, including any keywords and arguments, press the Enter key to submit the command to the command interpreter.

A command might require one or more arguments. To determine the keywords and arguments required for a command, refer to the command syntax. The syntax provides the pattern, or format, that must be used when entering a command.

For instance, the syntax for using the description command is description string. 

The argument is a string value provided by the user. The description command is typically used to identify the purpose of an interface.

The following examples demonstrate conventions used to document and use IOS commands:

**ping** *ip-address* - The command is ping and the user-defined argument is the ip-address of the destination device. For example, ping 10.10.10.5.

**traceroute** *ip-address* - The command is traceroute and the user-defined argument is the ip-address of the destination device. For example, traceroute 192.168.254.254.

If a command is complex with multiple arguments, you may see it represented like this:

```bash
  Switch(config-if)# switchport port-security aging {  static | time time |     type   {absolute | inactivity}
```

The command will typically be followed with a detailed description of the command and each argument.

The Cisco IOS Command Reference is the ultimate source of information for a particular IOS command.

- Help features

The IOS has two forms of help available: context-sensitive help and command syntax check.

Context-sensitive help enables you to quickly find answers to these questions:

**Which commands are available in each command mode?**
**Which commands start with specific characters or group of characters?**
**Which arguments and keywords are available to particular commands?**

To access context-sensitive help, simply enter a question mark, ?, at the CLI.

Command syntax check verifies that a valid command was entered by the user. When a command is entered, the command line interpreter evaluates the command from left to right. If the interpreter understands the command, the requested action is executed, and the CLI returns to the appropriate prompt. However, if the interpreter cannot understand the command being entered, it will provide feedback describing what is wrong with the command.


```bash
Switch> ?
```
- connect
- disable
- disconnect
- enable
- exit
- logout
- ping
- resume
- show
- telnet
- terminal
- trace-route

```bash
Switch(config)# in?
```
- interface

This shows the argumet or parameter after the command

```bash
Switch(config)# interface ?
```

- Ethernet
- FastEthernet
- GigabitEthernet
- Port-channel
- Clan
- range
#### Hot keys and Shortcuts

The IOS CLI provides hot keys and shortcuts that make configuring, monitoring, and troubleshooting easier.

Commands and keywords can be shortened to the minimum number of characters that identify a unique selection. For example, the configure command can be shortened to conf because configure is the only command that begins with conf. An even shorter version, con, will not work because more than one command begins with con. Keywords can also be shortened.

The table lists keystrokes to enhance command line editing.

Key stroke | Description

**Tab** | completes a partial command name entry ( con tab wont work and there is more than 1 commands)

Backspace | Erases the character to the lft of the cursor

ctrl+D | erases the chracter at the cursor

ctrl K | Erases characters from the cursor to the end of comman line

esc D | erases all characters from the cursor to the end of the word 

Ctrl U or ctrl x | erases all characters from the cursor back to the beginnning of the comman line 

ctrl W | erases the word to the left of cursor 

**ctrl A** | moves cursor to the beginnning to the left 
**ctrl E** | moves the cursor to the end of command line 

left arrow or ctrl B | moves cursor one character to the left 

esc B | moves the cursor back one word to the left 

esc F | moves the cursor forward one word to the right 

right arrow or ctrl F | moves the cursor one character to the right 


**up arrow or ctrl p**| recalls the previous command in the history buffer, beginning with the most recent command 

**down arrow or ctrl n** | goes to the next line in the history buffer

**ctrl r or ctrl I or ctrl L**| redisplays the system prompt and comman line after a console message is recevied. 


Note: While the Delete key typically deletes the character to the right of the prompt, the IOS command structure does not recognize the Delete key.

When a command output produces more text than can be displayed in a terminal window, the IOS will display a “--More--” prompt. The following table describes the keystrokes that can be used when this prompt is displayed.

- Enter key displays the next line 
- space bar displays the next screen 
- any other key ends the display string, returning to the previous prompt ( except y which answers yes to the more promp and acts like the space bar)
  
This table lists commands used to exit out of an operation.


**ctrl c**| when in any configuration mode, ends the configuration mode and returns to privilged exe vmode. when in set up mode, aborts back to the comman promt 
**ctrl z** | when in config mode, ends the config mode and return to privileged exec mode 



**ctrl shift 6** | all purpose break sequence used to abort DNS lookups, traceroutes, pings etc 


### 2.4 Basic Device Configuration

### 2.4.1 Device Names
Now, you are ready to configure devices! The first configuration command on any device should be to give it a unique device name or hostname. By default, all devices are assigned a factory default name. For example, a Cisco IOS switch is "Switch."

The problem is if all switches in a network were left with their default names, it would be difficult to identify a specific device. For instance, how would you know that you are connected to the right device when accessing it remotely using SSH? The hostname provides confirmation that you are connected to the correct device.
The default name should be changed to something more descriptive. By choosing names wisely, it is easier to remember, document, and identify network devices. Here are some important naming guidelines for hosts:

• Start with a letter
• Contain no spaces
• End with a letter or digit
• Use only letters, digits, and dashes
• Be less than 64 characters in length

An organization must choose a naming convention that makes it easy and intuitive to identify a specific device. The hostnames used in the device IOS preserve capitalization and lowercase characters. For example, the figure shows that three switches, spanning three different floors, are interconnected together in a network.
The naming convention that was used incorporated the location and the purpose of each device. Network documentation should explain how these names were chosen so additional devices can be named accordingly.
When the naming convention has been identified, the next step is to use the CLI to apply the names to the devices. As shown in the example, from the privileged EXEC mode, access the global configuration mode by entering the configure terminal command. Notice the change in the command prompt.

```bash
Switch# configure terminal
Switch (config)# hostname Sw-Floor-1
Sw-Floor-1 (config) #
```

From global configuration mode, enter the command hostname followed by the name of the switch and press Enter. Notice the change in the command prompt name.
Note: To return the switch to the default prompt, use the no hostname global config command.
Always make sure the documentation is updated each time a device is added or modified. Identify devices in the documentation by their location, purpose, and address.

###  2.4.2 Password Guidelines
The use of weak or easily guessed passwords continues to be the biggest security concern of organizations. Network devices, including home wireless routers, should always have passwords configured to limit administrative access.
Cisco IOS can be configured to use hierarchical mode passwords to allow different access privileges to a network device.
All networking devices should limit administrative access by securing privileged
EXEC, user EXEC, and remote Telnet access with passwords. In addition, all passwords should be encrypted and legal notifications provided.
When choosing passwords, use strong passwords that are not easily guessed. There are some key points to consider when choosing passwords:
• Use passwords that are more than eight characters in length.
• Use a combination of upper and lowercase letters, numbers, special characters, and/or numeric sequences.
• Avoid using the same password for all devices.
• Do not use common words because they are easily guessed.
Use an internet search to find a password generator. Many will allow you to set the length, character set, and other parameters.
Note: Most of the labs in this course use simple passwords such as cisco or class.
These passwords are considered weak and easily guessable and should be avoided in production environments. We only use these passwords for convenience in a classroom setting, or to illustrate configuration examples.

###  2.4.3 Configure Password


When you initially connect to a device, you are in user EXEC mode. This mode is secured using the console.
To secure user EXEC mode access, enter line console configuration mode using the line console 0 global configuration command, as shown in the example. The zero is used to represent the first (and in most cases the only) console interface. Next, specity the user EXEC mode password using the password password command.
Finally, enable user EXEC access using the login command.
```bash
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line console 0
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login Sw-Floor-1(config-line) # end
Sw-Floor-1#
```

Console access will now require a password before allowing access to the user EXEC mode.
To have administrator access to all IOS commands including configuring a device, you must gain privileged EXEC mode access. It is the most important access method because it provides complete access to the device.
To secure privileged EXEC access, use the enable secret password global config command, as shown in the example.

```bash

Sw-Floor-1# configure terminal
Sw-Floor-1 (config)# enable secret class
Sw-Floor-1(config) # exit
Sw-Floor-1#
```

Virtual terminal (VTY) lines enable remote access using Telnet or SSH to the device.
Many Cisco switches support up to 16 VTY lines that are numbered 0 to 15.
To secure VTY lines, enter line VTY mode using the line vty 0 15 global config command. Next, specify the VTY password using the password password command. Lastly, enable VTY access using the login command.
An example of securing the VTY lines on a switch is shown.
```bash
Sw-Floor-1# configure terminal
Sw-Floor-1 (config)# line vty 0 15
Sw-Floor-1 (config-line)# password cisco
Sw-Floor-1 (config-line)# login
Sw-Floor-1 (config-line)# end
Sw-Floor-1# 
```

###  2.4.4 Encrypt Password

The startup-config and running-config files display most passwords in plaintext. This is a security threat because anyone can discover the passwords if they have access to these files.
To encrypt all plaintext passwords, use the service password-encryption global config command as shown in the example.
```bash 
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# service password-encryption
Sw-Floor-1(config) #
```

The command applies weak encryption to all unencrypted passwords. This encryption applies only to passwords in the configuration file, not to passwords as they are sent over the network. The purpose of this command is to keep unauthorized individuals from viewing passwords in the configuration file.
Use the show running-config command to verify that passwords are now encrypted.

```bash 
Sw-Floor-1(config)# end
Sw-Floor-1# show running-config
!
(Output omitted)
!
line con o
password 7 094F471A1A0A
login
!
line vty 0 4
password 7 094F471A1A0A
login
line vty 5 15
password 7 094F471A1A0A
login
!
end
```
### 2.4.5 Banner Message

Althouch recuiring passwords is one way to keep unauthorized personnel out of a
Course content
HeroIn, ito vital to provide a method for declaring that only authorized personnel should attempt to access the device. To do this, add a banner to the device output.
Banners can be an important part of the legal process in the event that someone is prosecuted for breaking into a device. Some legal systems do not allow prosecution, or even the monitoring of users, unless a notification is visible.
To create a banner message of the day on a network device, use the banner motd # the message of the day # global config command. The "#" in the command syntax is called the delimiting character. It is entered before and after the message. The delimiting character can be any character as long as it does not occur in the message. For this reason, symbols such as the "#" are often used. After the command is executed, the banner will be displayed on all subsequent attempts to access the device until the banner is removed.
The following example shows the steps to configure the banner on Sw-Floor-1.

```bash 
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# banner motd #Authorized Access Only#
```

###### Quiz: 

What is the command to assign the name "Sw-Floor-2" to a switch?
A: hostname Sw-Floor-2

How is the privileged EXEC mode access secured on a switch?
A:enable secret class

Which command enables password authentication for user EXEC mode access on a switch?
A:login

Which command encrypts all plaintext passwords access on a switch?
a:service password-encryption

Which is the command to configure a banner to be displayed when connecting to a switch?
A:banner motd $ Keep out $

### 2.5 Save Configuration

### 2.5.1 Configuration Files 

You now know how to perform basic configuration on a switch, including passwords and banner messages. This topic will show you how to save your configurations.

There are two system files that store the device configuration:

startup-config - This is the saved configuration file that is stored in NVRAM. It contains all the commands that will be used by the device upon startup or reboot. Flash does not lose its contents when the device is powered off.
running-config - This is stored in Random Access Memory (RAM). It reflects the current configuration. Modifying a running configuration affects the operation of a Cisco device immediately. RAM is volatile memory. It loses all of its content when the device is powered off or restarted.
The show running-config privileged EXEC mode command is used to view the running config. As shown in the example, the command will list the complete configuration currently stored in RAM.
```bash 
Sw-Floor-1# show running-config
Building configuration...
Current configuration : 1351 bytes
!
! Last configuration change at 00:01:20 UTC Mon Mar 1 1993
!
version 15.0
no service pad
service timestamps debug datetime msec
service timestamps log datetime msec
service password-encryption
!
hostname Sw-Floor-1
!
(output omitted)
```
To view the startup configuration file, use the show startup-config privileged EXEC command.

If power to the device is lost, or if the device is restarted, all configuration changes will be lost unless they have been saved. To save changes made to the running configuration to the startup configuration file, use the copy running-config startup-config privileged EXEC mode command.

### 2.5.2 After the running Configuration  
If changes made to the running config do not have the desired effect and the running-config has not yet been saved, you can restore the device to its previous configuration. Remove the changed commands individually, or reload the device using the reload privileged EXEC mode command to restore the startup-config.

The downside to using the reload command to remove an unsaved running config is the brief amount of time the device will be offline, causing network downtime.

When a reload is initiated, the IOS will detect that the running config has changes that were not saved to the startup configuration. A prompt will appear to ask whether to save the changes. To discard the changes, enter n or no.

Alternatively, if undesired changes were saved to the startup config, it may be necessary to clear all the configurations. This requires erasing the startup config and restarting the device. The startup config is removed by using the erase startup-config privileged EXEC mode command. After the command is issued, the switch will prompt you for confirmation. Press Enter to accept.

After removing the startup config from NVRAM, reload the device to remove the current running config file from RAM. On reload, a switch will load the default startup config that originally shipped with the device.

"copy run start" is the short version of copy running-config startup-config.


### 2.5.1 Capture configuration to a text file 

Configuration files can also be saved and archived to a text document. This sequence of steps ensures that a working copy of the configuration file is available for editing or reuse later.

For example, assume that a switch has been configured, and the running config has been saved on the device.

Step 1. Open terminal emulation software, such as PuTTY or Tera Term, that is already connected to a switch.
Step 2. Enable logging in the terminal software and assign a name and file location to save the log file. The figure displays that All session output will be captured to the file specified (i.e., MySwitchLogs).
Step 3. Execute the show running-config or show startup-config command at the privileged EXEC prompt. Text displayed in the terminal window will be placed into the chosen file.
```bash 
Sw-Floor-1# show running-config
Building configuration...
(output omitted)
```
Step 4. Disable logging in the terminal software. The figure shows how to disable logging by choosing the None session logging option.
The text file created can be used as a record of how the device is currently implemented. The file could require editing before being used to restore a saved configuration to a device.

To restore a configuration file to a device:

Step 1. Enter global configuration mode on the device.

Step 2. Copy and paste the text file into the terminal window connected to the switch.

The text in the file will be applied as commands in the CLI and become the running configuration on the device. This is a convenient method of manually configuring a device.

### 2.6 Ports and Addresses
Congratulations, you have performed a basic device configuration! Of course, the fun is not over yet. If you want your end devices to communicate with each other, you must ensure that each of them has an appropriate IP address and is correctly connected. You will learn about IP addresses, device ports and the media used to connect devices in this topic.
Course content
The use of IP addresses is the primary means of enabling devices to locate one another and establish end-to-end communication on the internet. Each end device on a network must be configured with an IP address. Examples of end devices include these:
• Computers (work stations, laptops, file servers, web servers)
• Network printers
• VolP phones
• Security cameras
• Smart phones
• Mobile handheld devices (such as wireless barcode scanners)
The structure of an IPv4 address is called dotted decimal notation and is represented by four decimal numbers between 0 and 255. IPv4
addresses are assigned to individual devices connected to a network.
Note: IP in this course refers to both the IPv4 and IPv6 protocols. IPv6 is the most recent version of IP and is replacing the more common IPv4.
With the IPv4 address, a subnet mask is also necessary. An IPv4 subnet mask is a 32-bit value that differentiates the network portion of the address from the host portion. Coupled with the IPv4 address, the subnet mask determines to which subnet the device is a member.
The example in the figure displays the IPv4 address (192.168.1.10), subnet mask (255.255.255.0), and default gateway (192.168.1.1) assigned to a host. The default gateway address is the IP address of the router that the host will use to access remote networks, including the internet.

IPv6 addresses are 128 bits in length and written as a string of hexadecimal values. Every four bits is represented by a single hexadecimal digit; for a total of 32 hexadecimal values. Groups of four hexadecimal digits are separated by a colon (:) . IPv6 addresses are not case-
sensitive and can be written in either lowercase or uppercase.


Network communications depend on end user device intertaces. networkina device intertaces. and the cables that connect them. tacr
Network communications depend on end user device interfaces, networking device interfaces, and the cables that connect them. Each physical interface has specifications, or standards, that define it. A cable connecting to the interface must be designed to match the physical standards of the interface. Types of network media include twicturse contenner cables, fiber-optic cables, coaxial cables, or wireless, as shown in the figure.

Different types of network media have different features and benefits. Not all network media have the same characteristics. Not all media Course content e for the same purpose. These are some of the differences between various types of media:
• Distance the media can successfully carry a signal
• Environment in which the media is to be installed
• Amount of data and the speed at which it must be transmitted
• Cost of the media and installation
Not only does each link on the internet require a specific network media type, but each link also requires a particular network technology.
For example, Ethernet is the most common local-area network (LAN) technology used today. Ethernet ports are found on end-user devices, switch devices, and other networking devices that can physically connect to the network using a cable.
Cisco IOS Layer 2 switches have physical ports for devices to connect. These ports do not support Layer 3 IP addresses. Therefore, switches have one or more switch virtual interfaces (SVIs). These are virtual interfaces because there is no physical hardware on the device associated with it. An SVI is created in software.
The virtual interface lets you remotely manage a switch over a network using IPv4 and IPv6. Each switch comes with one SVI appearing in the default configuration "out-of-the-box." The default SVI is interface VLAN1.
Note: A Layer 2 switch does not need an IP address. The IP address assigned to the SVI is used to remotely access the switch. An IP address is not necessary for the switch to perform its operations.

###### Quiz: 
What si the strutcture of an IPv4 address called
A:dotted decimal format

How is an IPv4 address represented
A: four decimal numbers between 0 and 255 seperated by periods.

What type pf interface has no physical port associated with it?
Switch virtual interface (SVI)


### 2.7 Configure IP addressing
### 2.7.1 Manual IP address Configuration for End Devices
Much like you need your friends' telephone numbers to text or call them, end devices in your network need an IP address so that they can communicate with other devices on your network. In this topic, you will implement basic connectivity by configuring IP addressing on switches and PCs.


IPv4 address information can be entered into end devices manually, or automatically using Dynamic Host Configuration Protocol (DHCP).

To manually configure an IPv4 address on a Windows host, open the Control Panel > Network Sharing Center > Change adapter settings and choose the adapter. Next right-click and select Properties to display the Local Area Connection Properties.

Highlight Internet Protocol Version 4 (TCP/IPv4) and click Properties to open the Internet Protocol Version 4 (TCP/IPv4) Properties window. Configure the IPv4 address and subnet mask information, and default gateway.

Note: IPv6 addressing and configuration options are similar to IPv4.

Note: The DNS server addresses are the IPv4 and IPv6 addresses of the Domain Name System (DNS) servers, which are used to translate IP addresses to domain names, such as www.cisco.com.

### 2.7.2 Automatic IP address Configuration for End Devices
End devices typically default to using DHCP for automatic IPv4 address configuration. DHCP is a technology that is used in almost every network. The best way to understand why DHCP is so popular is by considering all the extra work that would have to take place without it.

In a network, DHCP enables automatic IPv4 address configuration for every end device that is DHCP-enabled. Imagine the amount of time it would take if every time you connected to the network, you had to manually enter the IPv4 address, the subnet mask, the default gateway, and the DNS server. Multiply that by every user and every device in an organization and you see the problem. Manual configuration also increases the chance of misconfiguration by duplicating another device’s IPv4 address.

As shown in the figure, to configure DHCP on a Windows PC, you only need to select Obtain an IP address automatically and Obtain DNS server address automatically. Your PC will search out a DHCP server and be assigned the address settings necessary to communicate on the network.

Note: IPv6 uses DHCPv6 and SLAAC (Stateless Address Autoconfiguration) for dynamic address allocation.

### Switch Virtual Interface Configuration
To access the switch remotely, an IP address and a subnet mask must be configured on the SVI. To configure an SVI on a switch, use the interface vlan 1 global configuration command. Vlan 1 is not an actual physical interface but a virtual one. Next assign an IPv4 address using the ip address ip-address subnet-mask interface configuration command. Finally, enable the virtual interface using the no shutdown interface configuration command.

After these commands are configured, the switch has all the IPv4 elements ready for communication over the network.

Note: Similar to a Windows hosts, switches configured with an IPv4 address will typically also need to have a default gateway assigned. This can be done using the ip default-gateway ip-address global configuration command. The ip-address parameter would be the IPv4 address of the local router on the network, as shown in the example. However, in this module you will only be configuring a network with switches and hosts. Routers will be introduced later.

```bash
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# interface vlan 1
Sw-Floor-1(config-if)# ip address 192.168.1.20 255.255.255.0
Sw-Floor-1(config-if)# no shutdown
Sw-Floor-1(config-if)# exit
Sw-Floor-1(config)# ip default-gateway 192.168.1.1
```


### 2.8 Verify connectivity
In the same way that you use commands and utilities like ipconfig to verify the network configuration of a PC host, you also use commands to verify the interfaces and address settings of intermediary devices like switches and routers.

# What did i learn in this module ?
Course content evices and network devices require an operating system (OS). The user can interact with the shell using a command-line interface (CLI) to use a keyboard to run CLI-based network programs, use a keyboard to enter text and text-based commands, and view output on a monitor.
As a security feature, the Cisco IOS software separates management access into the following two command modes: User EXEC Mode and Privileged EXEC Mode.
Global configuration mode is accessed before other specific configuration modes. From global config mode, the user can enter different subconfiguration modes. Each of these modes allows the configuration of a particular part or function of the lOS device. Two common subconfiguration modes include: Line Configuration Mode and Interface Configuration Mode. To move in and out of global configuration mode, use the configure terminal privileged EXEC mode command. To return to the privileged EXEC mode, enter the exit global config mode command.
Each IOS command has a specific format or syntax and can only be executed in the appropriate mode. The general syntax for a command is the command followed by any appropriate keywords and arguments. The IOS has two forms of help available: context-sensitive help and command syntax check.
The first configuration command on any device should be to give it a unique device name or hostname. Network devices should always have passwords configured to limit administrative access. Cisco IOS can be configured to use hierarchical mode passwords to allow different access privileges to a network device. Configure and encrypt all passwords. Provide a method for declaring that only authorized personnel should attempt to access the device by adding a banner to the device output.
There are two system files that store the device configuration: startup-config and running-config. Running configuration files can be altered if they have not been saved. Configuration files can also be saved and archived to a text document.
IP addresses enable devices to locate one another and establish end-to-end communication on the internet. Each end device on a network must be configured with an IP address. The structure of an IPv4 address is called dotted decimal notation and is represented by four decimal numbers between 0 and 255.
IPv4 address information can be entered into end devices manually, or automatically using Dynamic Host Configuration Protocol (DHCP). In a network, DHCP enables automatic IPv4 address configuration for every end device that is DHCP-enabled. To access the switch remotely, an IP address and a subnet mask must be configured on the SVI. To configure an SVI on a switch, use the interface vlan 1 command in global configuration mode.
In the same way that you use commands and utilities to verify a PC host's network configuration, you also use commands to verify the interfaces and address settings of intermediary devices like switches and routers. The show ip interface brief command verifies the condition of the switch interfaces. The ping command can be used to test connectivity to another device on the network or a website on the internet.


###### Quiz: 
Which statement is true about the running configuration file in a Cisco lOS device?
A:It affects the operation of the device immediately when modified.


Which two statements are true regarding the user EXEC mode? (Choose two.)
Only some aspects of the router configuration can be viewed.
The device prompt for this mode ends with the '>' symbol

Which type of access is secured on a Cisco router or switch with the enable secret command?
Privileged EXEC


What is the default SVI on a Cisco switch?
VLAN1

When a hostname is configured through the Cisco CLI, which three naming conventions are part of the guidelines? (Choose three.)
The hostname should contain no spaces
The hostname should begin with a letter
The hostname should be fewer than 64 characters in length

What is the function of the shell in an OS?
It interfaces between the users and the kernel.

A router with a valid operating system contains a configuration file stored in NVRAM. The configuration file has an enable secret password but no console password. When the router boots up, which mode will display?
User EXEC mode

An administrator has just changed the IP address of an interface on an lOS device. What else must be done in order to apply those changes to the device?
Nothing must be done. Changes to the configuration on an IOS device take effect as soon as the command is typed correctly and the Enter key has been pressed.



Which memory location on a Cisco router or switch will lose all content when the device is restarted?
RAM


Why would a technician enter the command copy startup-config running-config?
To copy an existing configuration into RAM


Which functionality is provided by DHCP?
Automatic assignment of an IP address to each host

Which two tunctions are provided to users by the context-sensitive help feature of the Cisco IOS CLI? (Choose two.)
Displaying a list of all available commands within the current mode
Determining which option, keyword, or argument is available for the entered command
Displaying a list of all avaiable commands within the current mode


Which memory location on a Cisco router or switch stores the startup configuration file?
NVRAM


To what subnet does the IP address 10.1.100.50 belong if a subnet mask of 255.255.0.0 is used?
10.1.0.0