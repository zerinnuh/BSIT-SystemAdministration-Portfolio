Week 3 - Enterprise Server Deployment and Operating System Installation

This repository contains my Week 3 portfolio project for ITEP 414 - System Administration and Maintenance. It documents my Ubuntu Server deployment, server verification, study of BIOS and UEFI, Ubuntu boot process flowchart, Windows Server installation, and comparison of enterprise server operating systems.

Project Overview

For this project, I worked as a Junior System Administrator tasked with preparing a server for ABC Startup Solutions. I installed Ubuntu Server in a virtual machine and configured the essential settings needed for future services such as file sharing, remote administration, database hosting, web hosting, and internal company applications.

I also verified that the server was working correctly, enabled secure remote access through SSH, created an Ubuntu boot process flowchart, installed Windows Server Evaluation, and compared Ubuntu Server, Windows Server, and Rocky Linux.

Learning Objectives

Through this project, I was able to:

Install and configure Ubuntu Server in a virtual environment.

Configure a hostname, user account, storage, network connection, and SSH service.

Use Linux commands to verify server functionality.

Explain the differences between BIOS and UEFI.

Illustrate the Ubuntu boot process.

Install Windows Server Evaluation in a separate virtual machine.

Compare commonly used enterprise server operating systems.

Create clear technical documentation for future administrators.

Virtual Machine Specifications

Component

Ubuntu Server Configuration

Virtual machine name

Ubuntu-Server-Week03

Operating system

Ubuntu Server LTS

Memory

4 GB RAM

Processor

2 virtual processors

Storage

40 GB virtual disk

Network

NAT with DHCP

Hostname

server01

Disk configuration

Guided - Use Entire Disk

Remote access

OpenSSH Server

What I Did

1. Created the Virtual Machine

I created a virtual machine named Ubuntu-Server-Week03. I assigned 4 GB of RAM, two virtual processors, and a 40 GB virtual disk. I configured the network adapter to use NAT and attached the Ubuntu Server LTS ISO to the virtual optical drive.

2. Installed Ubuntu Server

I started the virtual machine and completed the Ubuntu Server installation. I selected English as the language, used the English (US) keyboard layout, and allowed DHCP to configure the network. I assigned server01 as the hostname and created a non-root administrative user with a strong password.

For storage, I selected Guided - Use Entire Disk. I enabled Install OpenSSH Server so the server could support secure remote administration. After the installation was completed, I restarted the virtual machine and removed the installation ISO.

3. Verified the Server

After logging in, I verified the server using the following commands:

hostname
ip addr
ping -c 4 google.com
sudo apt update
sudo apt upgrade -y
systemctl status ssh

The verification confirmed that:

I could log in using the administrative account I created.

The configured hostname was server01.

The server received an IP address through DHCP.

The server had a working internet connection.

The package lists and installed packages were updated.

The SSH service was installed and displayed active (running).

BIOS vs UEFI Highlights

Feature

BIOS

UEFI

Full name

Basic Input/Output System

Unified Extensible Firmware Interface

Boot method

Reads boot code from the Master Boot Record

Loads an EFI application from the EFI System Partition

Partition style

MBR

GPT

Disk support

Generally limited to about 2 TB with MBR

Supports disks larger than 2 TB with GPT

Security

Does not provide native Secure Boot

Supports Secure Boot

Startup

Older and generally slower

Modern and generally faster

Typical use

Legacy computers

Modern computers and servers

UEFI has largely replaced BIOS because it supports modern hardware, larger storage devices, GPT partitioning, Secure Boot, and a more flexible startup environment. These features make UEFI more appropriate for current enterprise systems.

Ubuntu Boot Process



The Ubuntu startup sequence follows these stages:

Power On

BIOS or UEFI Initialization

Boot Device Detection

GRUB Boot Loader

Linux Kernel

init/systemd

System Services Start

Login Prompt

Windows Server Installation

I created a separate virtual machine and installed Windows Server Evaluation. During the installation, I selected the required operating system edition, configured the virtual disk, assigned a computer name, created an administrator password, and successfully logged in. I captured screenshots of the important installation and configuration stages for documentation.

Enterprise Operating System Comparison

Category

Ubuntu Server

Windows Server

Rocky Linux

Licensing

Free and open source

Commercial license

Free and open source

User interface

Primarily command line

Graphical interface and PowerShell

Primarily command line

Package management

APT and DEB

Windows Update, MSI, and Winget

DNF and RPM

Security

AppArmor, firewall, and security updates

Microsoft Defender, Active Directory, Group Policy, and firewall

SELinux, firewall, and enterprise-focused updates

Performance

Lightweight and efficient

Requires more system resources

Stable and efficient

Common uses

Web, cloud, database, and application servers

Active Directory, file services, and Microsoft applications

Enterprise hosting, databases, and Red Hat-compatible workloads

Main advantage

Large community and extensive software support

Strong integration with Microsoft services

Enterprise stability and RHEL compatibility

Main disadvantage

Some tasks require command-line knowledge

Licensing cost and higher hardware requirements

Smaller community than Ubuntu

Challenges Encountered

During the activity, I encountered issues related to the virtual machine's boot order, network connection, and installation media. I resolved them by confirming that the Ubuntu ISO was attached to the virtual optical drive, placing the optical drive first in the boot order, checking that the network adapter was enabled and set to NAT, and removing the ISO after the installation. I also verified the SSH service after installation to ensure that remote administration was available.

Reflection

Completing this project gave me practical experience in deploying and verifying server operating systems. Before this activity, I understood that servers provide services to users and other computers, but the installation process showed me how many configuration decisions must be completed before a server becomes ready for use. I learned to plan the virtual hardware, attach the correct installation media, configure the network, create an administrative account, prepare the disk, and enable services such as SSH.

The Ubuntu Server verification tasks were an important part of the project because they proved that the installation was functional. Using hostname confirmed the identity of the server, while ip addr displayed its network configuration. The ping test allowed me to check internet connectivity. Running apt update and apt upgrade taught me that a newly installed server should be updated before it is used in a production environment. I also used systemctl status ssh to verify that the SSH service was active and available for remote administration.

Studying BIOS and UEFI helped me understand what happens before the operating system loads. I learned that UEFI is designed for modern computers because it supports GPT, larger storage devices, faster startup, and Secure Boot. Creating the boot process flowchart also helped me visualize how the firmware, GRUB boot loader, Linux kernel, systemd, services, and login prompt work together during startup.

Installing Windows Server and comparing it with Ubuntu Server and Rocky Linux showed me that each operating system has different strengths. Windows Server is suitable for organizations that depend on Microsoft technologies, while Ubuntu Server is widely used for web, cloud, and application hosting. Rocky Linux provides enterprise stability and compatibility with the Red Hat ecosystem.

Overall, this project improved my technical skills, troubleshooting ability, and confidence in server administration. It also showed me that complete documentation is essential because it allows another administrator to understand, reproduce, maintain, or troubleshoot a server deployment.