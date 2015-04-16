#WMI Toolset

As part of system administration there is always a need that arises when Viruses are deployed/found on a network. Most commonly these needs are around finding specific files on windows clients as well as which application are currently running in the task list or if a file exists on a windows client. 
The most common way is to get internal/desktop support guys to go and investigate the windows clients which is very timeous OR to buy some expensive software that can be executed remotely (after client installs) and then reports can be pulled from them.


The WMI Toolkit, allows administrators to get all this information from their Linux Machines. The can see which processes are running within a network as the tools within the framework allow for whole CIDR ranges to be checked. Because this is WMIC through RPC and SMB you will need valid logon credentials for each computer OR a Domain Administrator account for whole domains.



#The Toolkit currently provides these tools:


1.LRRWP - Locate Remote Running Windows Processes
    
    This app runs to find processes that are running on windows clients. 



2.RWFX - Remote Windows file exists

    This tools can file a specific file on a windows client / CIDR range to determine if a Virus is present



3.RWHI - Remote Windows Hardware Info (Memory, Bios, Motherboard, CPU)

    This tool can display the hardware info for all windows clients/ with extensive information.



4.RWHS - Remote Windows Shares

    Use this tool to locate Remote windows shares and their respective properties.
    This help in detecting unwanted shares on a network to Help fight against data loss or theft.



#Hints

Pipe the tools's output on stdout to a file and grep it for the process you are looking for.

eg. 

    host@time>LRRWP 192.168.1.0/24 domain user password > output.txt 

    host@time>cat output.txt | grep -i backdoor.exe


This will show you matching records found:

    192.168.1.23  backdoor.exe

    192.168.1.187 backdoor.exe



#Additional Info

This toolset will alow the user to query the WMIC from linux.
It is important to notice that the WMIC libraries need to be installed on your distro
As part of this toolset I have provided the packages that need to be installed. The provided libs are for debian.



To install the libraries run the install.sh file





 (you will need root)

Regards
Jacques Coetzee
