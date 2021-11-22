*******************************************************************************
** c2005-2011 Xilinx, Inc. All Rights Reserved.
** Confidential and proprietary information of Xilinx, Inc.
*******************************************************************************
**   ____  ____ 
**  /   /\/   / 
** /___/  \  /   Vendor: Xilinx 
** \   \   \/    Version: 1.057 
**  \   \        Filename: readme.txt 
**  /   /        Date Last Modified:  Fri Apr 8 2011 
** /___/   /\    Date Created: Tue Mar 4 2008 
** \   \  /  \ 
**  \___\/\___\ 
** 
**Device:
**Purpose:
**    Linux driver installer for the Xilinx Parallel IV and Platform Cable USB
**    download cables.
**Reference: 
**Revision History:
**    1.033: Cd to the install_drivers directory.
**    1.035: Add check for write permission to the install_drivers directory.
**           Updated windrvr6 to version 9.00.
**           Used modprobe in loading the xpc4drvr 2.6 driver.
**    1.051: Added support for xp2 and xse.
**    1.052: Fixed version of xusbdfwu.rules
**    1.053: Unset ARCH environment variable prior to building drivers.
**    1.055: Return 20 if fxload is not found.
**           Return 21 if driver directory is not accessible.
**           Return 22 if user does not have root privileges.
**			 Convert windriver to version 9.20.
**    1.056: Added check for install log file to query for previous
**			 installation.
**    1.057: Added digilent plugin installer.
**    1.100: Updated windriver to version 10.3.1.
*******************************************************************************
**
**  Disclaimer: 
**		LIMITED WARRANTY AND DISCLAIMER. These designs are
**		Xilinx licenses this Design to you "AS-IS" with no warranty of any kind.  
**		Xilinx does not warrant that the functions contained in the Design will 
**		meet your requirements,that the Design will operate uninterrupted or be 
**		error-free, or that errors or bugs in the Design will be corrected.  
**		Xilinx makes no warranties or representations in regard to the results 
**		obtained from your use of the Design with respect to accuracy, reliability, 
**		or otherwise.  
**
**		XILINX MAKES NO REPRESENTATIONS OR WARRANTIES, WHETHER EXPRESS OR IMPLIED, 
**		STATUTORY OR OTHERWISE, INCLUDING, WITHOUT LIMITATION, IMPLIED WARRANTIES 
**		OF MERCHANTABILITY, NONINFRINGEMENT, OR FITNESS FOR A PARTICULAR PURPOSE. 
**		IN NO EVENT WILL XILINX BE LIABLE FOR ANY LOSS OF DATA, LOST PROFITS, OR FOR 
**		ANY SPECIAL, INCIDENTAL, CONSEQUENTIAL, OR INDIRECT DAMAGES ARISING FROM 
**		YOUR USE OF THIS DESIGN. 
**
*******************************************************************************

** IMPORTANT NOTES **

A step-by-step procedure for using this installer is provided. 

The latest revision of this installer package is available at:

https://secure.xilinx.com/webreg/clickthrough.do?cid=103670

First-time users should review UG344 "USB Cable Installation Guide" 
prior to running this installer. The latest revision of UG344 is available
at:

http://www.xilinx.com/bvdocs/userguides/ug344.pdf

*******************************************************************************

Running the installer:

Note: Root permission is required to perform the steps described in this section.

1) Disconnect all Xilinx USB cables from the host computer.
2) Open a shell or terminal console.
3) Extract the driver script and its support files to a local drive of the machine
where the cable will be used by typing:
tar xzvf install_drivers.tar.gz
The extraction creates a directory named install_drivers in the current directory.
4) Navigate to the install_drivers directory by typing:
cd install_drivers
5) Run the script by typing:
./install_drivers
6) When the installation is complete, reconnect the cable.
7. Change permissions on the USB / PC4 driver by typing: chmod 666 /dev/windrvr6. 

NOTE: By default, access to windrvr6 is restricted to root only. This step grants group and user access to the driver. However, if you reboot your system, access to the driver will revert back to root-only and you will have to repeat step #7 (you do not have to rerun the installation script). 

If the STATUS indicator on the cable illuminates, then the driver installation completed
successfully.

