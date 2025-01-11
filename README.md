<img src="https://www.safesystems.com/wp-content/uploads/2020/04/Microsofts-LDAP-Security-Update-and-the-Impact-on-Financial-Institutions-Today-Header-Blog-Image.png" alt="Traffic Examination"/>


<h1>Active Directory Project</h1>
Creating and provisioning a virtual Active Directory server and a client node to simulate how to manage users and computers. <br />

<h2>Lab Report: Active Directory Setup in VMware</h2>

Title
Basic Active Directory Lab with VMware Workstation Pro

Abstract
This lab demonstrates the setup of a simple Active Directory (AD) domain environment using VMware Workstation Pro. A Windows Server 2019 machine is configured as a Domain Controller (DC) with Active Directory Domain Services (AD DS), DNS, and DHCP. A Windows 10 client is connected to the domain for testing. The objective is to understand the roles of DHCP, DNS, and NAT in a virtualized AD setup.

Introduction
The purpose of this lab is to create a basic domain environment using VMware Workstation Pro. The lab consists of:
A Windows Server 2019 machine configured as a Domain Controller with DHCP, DNS, and NAT functionalities.
A Windows 10 machine as a client that joins the domain.
The domain name is configured as mydomain.com.

Materials and Methods
Materials
VMware Workstation Pro
Windows Server 2019 ISO
Windows 10 ISO
Methods
Network Configuration:


Two virtual networks were created: Internet and Internal.
The Domain Controller (DC) has two NICs:
NIC 1 (Internet): Receives an IP address via DHCP from the home router.
NIC 2 (Internal): Assigned a static IP address 172.16.0.1 with subnet mask 255.255.255.0.
Server Configuration:


Installed Windows Server 2019.
Configured AD DS and promoted the server to a Domain Controller with the Fully Qualified Domain Name (FQDN) mydomain.com.
Enabled DHCP on the Internal NIC with the following configuration:
IP Range: 172.16.0.100-200
Subnet Mask: 255.255.255.0
Gateway: 172.16.0.1
DNS Server: 172.16.0.1
Client Configuration:


Installed Windows 10.
Configured the NIC to receive IP settings automatically from the DC's DHCP server.
Joined the mydomain.com domain.
Testing:


Verified connectivity between the client and the server.
Tested domain authentication by logging in with domain user credentials.

Results
The Domain Controller was successfully configured with AD DS, DNS, and DHCP.
The Windows 10 client obtained an IP address from the DHCP server and successfully joined the domain mydomain.com.
Domain authentication and name resolution worked as expected.

Discussion
This lab illustrates the basic setup of an Active Directory environment in a virtualized network using VMware. Key observations include:
The importance of proper network segmentation (Internet vs. Internal) for domain isolation.
The role of DHCP and DNS in automating client configuration and domain name resolution.
NAT allowed the Domain Controller to provide internet access to the internal network.
Limitations:
Only a single client was tested. Scaling the domain with multiple clients and Group Policy Objects (GPOs) would require further configuration.

Conclusion
The lab successfully demonstrated the setup of a basic Active Directory environment using Windows Server 2019 and a Windows 10 client. This configuration can serve as a foundation for exploring advanced domain features such as GPOs, user authentication, and resource sharing.

References
Microsoft Windows Server 2019 Documentation
VMware Workstation Pro User Guide


