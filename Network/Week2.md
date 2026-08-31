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

### 2.4 Basic Device Configuration

### 2.5 Save Configuration

### 2.6 Ports and Addresses

### 2.7 Configure IP addressing

### 2.8 Verify connectivity

###### Quiz: 

