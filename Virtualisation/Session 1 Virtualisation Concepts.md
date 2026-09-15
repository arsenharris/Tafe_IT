# Session 1

### **Basic Computer Components**

**Central Processing Unit (CPU):** The CPU is the brain of the computer, responsible for executing instructions and processing data.

**Memory (RAM):** Random Access Memory (RAM) is the temporary storage that the CPU uses to store data and instructions while performing tasks.

**Storage:** This refers to the permanent storage of data, typically on hard drives (HDD) or solid-state drives (SSD).

**Motherboard:** The motherboard is the main circuit board that connects all components of the computer, allowing them to communicate with each other.

**Input/Output Devices:** These include peripherals like keyboards, mice, monitors, and printers that allow users to interact with the computer.

#### The Central Processing Unit (CPU)

The Central Processing Unit (CPU) is the core component of a computer that performs most of the processing inside a computer. It executes instructions from programs, performing basic arithmetic, logic, control, and input/output operations specified by the instructions.

There are many architectures for CPUs, but the most common in personal computers are x86 and ARM architectures. 

**The CPU's performance is often measured in terms of clock speed (GHz), number of cores, and cache size.**

**CPU Architectures**

- Different CPU architectures have different instruction sets, which can affect software compatibility and performance. For example, x86 architecture is commonly used in desktops and laptops, while ARM architecture is prevalent in mobile devices and some servers. This means you traditionally cannot run software compiled for one architecture on a different architecture without some form of translation or emulation.

*How to find your computers CPU information?*
- Windows 

```bash 
Get-WmiObject Win32_Processor | Select-Object Name, NumberOfCores, MaxClockSpeed
```

- Linux 

```bash 
lscpu
```

- macOS 

```bash 
sysctl -n machdep.cpu.brand_string
```

#### Main Memory (RAM)

RAM (Random Access Memory) is a type of **volatile** memory that temporarily stores data and instructions that the CPU needs while performing tasks. It allows for quick read and write access, enabling the CPU to access data much faster than it would from permanent storage.

There are different types of RAM, such as DRAM (Dynamic RAM) and SRAM (Static RAM), each with its own characteristics in terms of speed and cost. The amount of RAM in a system can significantly impact its performance, especially when running multiple applications or handling large datasets.


#### Secondary Storage

Secondary storage refers to **non-volatile** storage devices that retain data even when the computer is powered off. Common types of secondary storage include Hard Disk Drives (HDDs) and Solid State Drives (SSDs). HDDs use spinning disks to read/write data, while SSDs use flash memory, resulting in faster data access speeds.


#### Input/Output Devices 

Input/Output (I/O) devices are peripherals that allow users to interact with the computer system. Input devices, such as keyboards and mice, enable users to provide data and commands to the computer. Output devices, like monitors and printers, display or produce the results of the computer's processing.

#### The Motherboard

The motherboard is the main printed circuit board (PCB) in a computer that connects and allows communication between all the components, including the CPU, RAM, storage devices, and I/O devices. It contains slots for expansion cards, connectors for power and data cables, and various chips that manage data flow and system functions.

##### Modern Workload Challenges

Modern computing workloads present several challenges that virtualisation aims to address:

- **Resource Utilisation:** Many applications do not fully utilise the available hardware resources, leading to inefficiencies. Virtualisation allows multiple workloads to share the same physical resources, improving overall utilisation.

- **Isolation:** Running multiple applications on the same physical machine can lead to conflicts and security issues. Virtualisation provides isolation between workloads, enhancing security and stability.

- **Scalability:** As demand for computing resources fluctuates, virtualisation enables dynamic allocation and scaling of resources to meet changing needs.

- **Management Complexity:** Managing physical hardware can be complex and time-consuming. Virtualisation simplifies management by allowing administrators to manage virtual machines and resources through software.

- **Legacy Software Support:** Many organisations rely on legacy applications that may not be compatible with modern hardware or operating systems. Virtualisation and emulation can help run these applications in a compatible environment.

### **Emulation** ( like translator)

Emulation is the *process of mimicking* the behavior of one computer system (the guest) on another computer system (the host). This is typically achieved through software that replicates the hardware and software environment of the guest system, allowing applications designed for the guest to run on the host.

#### How Emulation Works

Emulation allows software designed for one architecture (e.g., ARM) to run on a completely different architecture (e.g., x86) by translating instructions in real-time. 
This translation process can be slow because every instruction must be converted, but it provides complete hardware compatibility. 
This is also how video game console emulators work, allowing games from older consoles to run on modern PCs.

#### Emulation in Gaming

Emulation is widely used in the gaming community to run games from older consoles on modern hardware. Consoles have unique hardware architectures, and emulators replicate these environments on contemporary systems. Some consoles achieve backward compatibility through built-in hardware or software emulation, allowing them to run games from previous generations.

This image shows how a system (the Sega Mega Drive) running a Motorola 68000 CPU can have its instruction set emulated on a modern x86 CPU, allowing games designed for the Mega Drive to run on contemporary hardware.

### **Virtualisation**

Virtualisation is the *process of creating virtual versions* of physical computing resources, such as servers, storage devices, and networks. It allows multiple virtual machines (VMs) to run on a single physical host, sharing its resources while remaining isolated from each other.

There are several types of virtualisation, including:

**Full Virtualisation:** The hypervisor emulates some components and shares the underlying hardware, allowing unmodified guest operating systems to run.

**Paravirtualisation:** The guest operating system is modified to interact directly with the hypervisor, improving performance.

**Containerisation:** Applications run in isolated user spaces (containers) on the same operating system kernel, sharing resources more efficiently.

#### How Virtualisation Works

Unlike emulation, virtualisation allows multiple guest operating systems to run on the same architecture (e.g., x86 on x86), sharing physical resources efficiently. The hypervisor manages resource allocation and ensures each VM remains isolated. This is much faster than emulation because instructions don't need to be translated—they can execute directly on the CPU.

#### Benefits of Virtualisation
Virtualisation offers several benefits, including:

**Resource Efficiency:** Multiple VMs can run on a single physical host, maximising hardware utilisation.

**Isolation:** Each VM is isolated from others, enhancing security and stability.

**Flexibility:** VMs can be easily created, modified, and deleted, allowing for rapid deployment and scaling.

**Cost Savings:** By consolidating workloads onto fewer physical machines, organisations can reduce hardware and energy costs.

**Disaster Recovery:** Virtual machines can be backed up and restored more easily than physical machines, improving disaster recovery capabilities.

#### Common Virtualisation Platforms

Some popular virtualisation platforms include:

**VMware vSphere/ESXi:** A widely used enterprise-grade virtualisation platform.

**Microsoft Hyper-V:** A hypervisor-based virtualisation technology built into Windows Server.

**Oracle VirtualBox:** A free and open-source hypervisor for desktop virtualisation.

**KVM (Kernel-based Virtual Machine):** An open-source hypervisor built into the Linux kernel.

**Broadcom and VMWare:** Broadcom acquired VMware in 2022, a major player in the virtualisation market. After the aquisition, licensing and product strategies have changed causing some controversy in the tech community.

#### Virtualisation Hardware Support

Modern CPUs often include hardware-assisted virtualisation features that improve the performance and efficiency of virtual machines. These features include:

**Intel VT-x:** Intel's hardware virtualisation technology that provides extensions to the x86 architecture to support efficient virtualisation.

**AMD-V:** AMD's equivalent technology that offers similar capabilities for AMD processors.

**IOMMU (Input-Output Memory Management Unit):** A hardware feature that allows direct memory access (DMA) remapping, improving performance and security for virtualised environments.

Some hardware components like network cards and storage controllers also support virtualisation, but others do not and must be emulated by the hypervisor.

#### Virtualisation Hardware Support

Virtualisation is a foundational technology for cloud computing. Cloud service providers use virtualisation to offer scalable and flexible computing resources to users on-demand. By leveraging virtualisation, cloud providers can efficiently manage large data centres and deliver services such as Infrastructure as a Service (IaaS) and Platform as a Service (PaaS).

Services like Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP) rely heavily on virtualisation to provide users with virtual machines, storage, and networking capabilities in a cost-effective manner.

**Cloud Mapping: Local vs Cloud-Managed Infrastructure**

In local virtualisation, you manage the physical host hardware yourself—you choose and maintain the CPU, RAM, storage, and hypervisor software (like VirtualBox or VMware). You have full control but also full responsibility for hardware maintenance and capacity planning.

In cloud virtualisation (like AWS EC2), the cloud provider manages the physical infrastructure for you. You simply request a virtual machine with specific resources (CPU, RAM, storage), and the provider allocates it from their data centre. This abstracts away hardware concerns, allowing you to focus on your workloads rather than maintaining physical servers.

Both approaches use virtualisation technology, but cloud computing shifts infrastructure management to the provider.

#### Para-virtualisation

Paravirtualisation is a virtualisation technique where *the guest operating system is modified to interact directly with the hypervisor.* This modification allows the guest OS to be aware of the virtualised environment, leading to improved performance compared to full emulation. This is because the guest OS can make hypercalls to the hypervisor for certain operations, reducing the overhead associated with emulating hardware.

This might be needed in situations where:

- The guest OS is open-source and can be modified (e.g., Linux).
- Performance is critical, and the overhead of full virtualisation or emulation is unacceptable.
- The hypervisor provides specific paravirtualisation drivers or interfaces that the guest OS can utilise.
- The underlying hardware does not support full virtualisation features.

#### Combined Virtualisation, Para-virtualisation and Emulation

In some scenarios, a combination of virtualisation, para-virtualisation, and emulation may be employed to achieve the desired performance and compatibility. For example, a hypervisor might use full virtualisation for most operations but rely on para-virtualisation for specific drivers or components to enhance performance. Additionally, emulation might be used for certain hardware devices that are not natively supported by the hypervisor.

For example, a virtual machine running on an x86 host might use full virtualisation for the CPU and memory, para-virtualisation for network and storage drivers, and emulation for legacy hardware devices that are not supported by the hypervisor (like a PS2 keyboard or GPU).

#### Local Hypervisor vs Cloud Instance: A Simple Comparison

Now that you understand virtualisation concepts, it's helpful to see how they apply in different contexts. The table below compares running virtual machines locally (on your own computer) versus in the cloud:

| Aspect | Local Hypervisor (e.g., VirtualBox) | Cloud Instance (e.g., AWS EC2) |
|---|---|---|
| **Hardware** | You own and manage the physical hardware | Provider manages the physical hardware |
| **Resource Limits** | Limited by your computer's specs | Scalable — request more resources as needed |
| **Cost Model** | One-time hardware purchase | Pay-as-you-go for resources used |
| **Setup Time** | Install hypervisor and configure manually | Launch an instance in minutes from the console |
| **Access** | Local access only (unless configured for remote access) | Accessible from anywhere via the internet |
| **Maintenance** | You handle hardware and software updates | Provider maintains the physical infrastructure |
| **Best For** | Learning, testing, isolated environments | Production workloads, scalability, remote access |


Dual-Track Learning Ahead
In this course, you'll experience both approaches:

Local virtualisation: You'll install a desktop hypervisor and create a minimal Fedora VM to understand the fundamentals hands-on.
Cloud virtualisation: You'll launch equivalent virtual machines in AWS to see how cloud platforms simplify deployment and management.
This dual-track approach helps you understand the technology deeply while preparing you for modern cloud-first workflows.

### Summary

In this session, we covered the fundamental concepts of basic computing, emulation, and virtualisation. We reviewed the primary components of a computer system, explored how emulation allows software to run on different architectures, and delved into the principles and benefits of virtualisation. Understanding these concepts is crucial for grasping more advanced topics in virtualisation and cloud computing that will be covered in subsequent sessions.
V