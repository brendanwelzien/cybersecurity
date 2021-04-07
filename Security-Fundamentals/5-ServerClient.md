# Protecting the Server and Client

## Malicious Software
- sometimes called malware, software designed to infiltrate a computer system
- associated with virus, worms, Trojan horses, spyware, roitkits and dishonest adware

**Virus**
- program that can copy itself and infect a computer without user's consent or knowledge
- early viruses were forms of executable code that was hidden in boot sector of a disk or executable file
- macro programs can be embedded within documents such as word processors and spreadsheets

**Polymorphic Virus**
- self-encrypted virus designed to avoid scanner detecting, upon infection it duplicates itself by creating usable/slightly modified copies of itself

**Worm**
- self-replicating program that replicates itself to other computers over network without user intervention
- different from a virus, a worm does not corrupt or modify files on a target computer
- consumes bandwidth as well as processor/memory resources, slowing system down or causing to be unusable
- worms spread by using security holes found within operating system or TCP/IP software implementations

**Trojan Horse and Spyware**
- Trojan horse is a program that appears as desirable or useful program, users tricked into loading and executing program on their system
- spyware is a type of malware that collects personal info or browsing habits without the user's knowledge

**Adware**
- Adware is a type of malware that automatically renders advertisements to generate revenue for its author
- ransomware, holding victim's data and threatens to publish unless ransom is paid

**rootkit and backdoor**
- rootkit is software or hardware device designed to gain admin-level control over computer system
- backdoor is a program that gives some remote, unauthorized control of a system or initiates an unauthorized task

## Protecting Against Malware
1. keep system up to date with latest service packs, security patches and other critical fixes
2. use up-to-date antivirus software package

**Virus Hoax**
- message warning the recipient of a non-existent computer virus threat usually sent as a chain email
    - this is a form of social engineering that play's on ignorance and fear

**Zero=Day**
- vulnerability which is an undisclosed computer-software vulnerability that hackers can exploit to adversely affect computer programs/data/networks
- "zero day" because it is not publicly reported or announced before becoming active, leaving the software's author with zero days in which to create patches or workaround to mitigate actions (hackers *get a jump start on a vulnerability*)
- *service pack* may include Microsoft's many fixes/patches released together

**WSUS and SCCM**
- For corporations, you can also use Windows Server Update Service (WSUS) or System Center Configuration Manager (SCCM) to keep your systems updates. 
- The advantages of using one of these two systems allow you to test the patch, schedule the updates and prioritize client updates. 
- When you consider the patch is safe to deploy, you then enable the patch for deployment.

**UAC User Account Control**
- feature that started with Windows Vista that helps prevent unauthorized changes to your computer
- protection from malware
- You can do the following without admin rights:
    Install Updated from Windows

    Install Drivers from Windows 

    View Settings

    Pair Bluetooth Devices

    Reset the network adapter and perform repair tasks

**Windows Firewall**
- A firewall can help prevent hackers or malicious software (such as worms) from gaining access to your computer through a network or the Internet. 
- A firewall can also help stop your computer from sending malicious software to other computers.
- Microsoft recommends that you should always use the Windows Firewall. 

**Offline Files**
- Offline files are copies of network files that are stored on your computer so that you can access them when you are not connected to the network or when the network folder with the files is not connected.
- Offline files are not encrypted unless you choose to do so. 
- You might want to encrypt your offline files if they contain sensitive or confidential information and you want to make them more secure by restricting access to them. 

**Client Security**
- user computers can be their own worst enemy
- lock down their computer and prevent them from making their personal installations, etc. which can cause harm
- use *Windows Defender* to protect computer and notify when there are malware attempts or when critical settings are trying to be changed

- use spam filtering system in efforts to protect emails

**Sender Polciy Framework (SPF)**
- Sender Policy Framework (SPF) is an email validation system designed to prevent e-mail spam done with source address spoofing. 
- SPF allows administrators to specify which hosts are allowed to send e-mail from a given domain as specified in a specific DNS SPF record in the public DNS. 
- If email for a domain is not sent from a host listed in the DNS SPF, it will be considered spam and blocked.

**SMTP Relay**
- One of the primary email protocols is SMTP. Simple Mail Transfer Protocol (SMTP) is used to transfer email from one server to another and it is responsible for outgoing mail transport. SMTP uses TCP port 25.
- While you may think that your email servers are only used for your users to send and retrieve email, they are also used to relay email. 
- Usually, you only want your internal servers to relay email through your mail servers. 
- Unfortunately, spammers look for unprotected SMTP servers to relay their email through. 

## Browsing Internet
- When you use a browser to access the Internet, a lot can be revealed about a person’s personality and personal information. 
- Therefore, you need to take steps to ensure that this information cannot be read or used without your knowledge.
- A cookie is a piece of text stored by a user’s web browser. 
- It can be used for a wide range of items including user identification, authentication, storing site preferences and shopping cart contents.
- To help manage Internet Explorer security when visiting sites, Internet Explorer divides your network connection into four content zones or types:
    - Internet Zone
    - Local Intranet Zone
    - Trusted Sites Zone
    - Restricted Sites Zone

**Phishing**
- Phishing is a technique based on social engineering. With phishing, users are asked (usually through email or other websites) to supply personal information by:
- Having an email asking your username, password and other personal information such as account numbers, PINs and social security numbers.
- Redirect a user to a convincing-looking web site that urges users to supply personal information, such as passwords and account numbers.
    - To help protect against Phishing, Internet Explorer 8 includes SmartScreen Filter that examines traffic for evidence of phishing activity and displays a warning to the user if it finds any. 

**Pharming**
- Pharming is a  attack aimed at redirecting a website's traffic to bogus website. 
- This is usually accomplished by changing the hosts file (a text that provides name resolution for host or domain names to IP address) on a computer or by exploiting a vulnerability on a DNS server. 

**SSL**
- When you surf the Internet, there are times when you need to transmit private data over the Internet such as credit card numbers, social security numbers and so on. 
- During these times, you should be using http over SSL (https) to encrypt the data sent over the Internet. 
- By convention, URLs that require an SSL connection start with https: instead of http:.

## Protecting Your Server
1. where to place server
    - server should be kept in a secure location
    - servers should be in their own subnet and VLAN to reduce traffic to the servers including broadcasts
2. harden the server where you reduce the surface of attack and you reduce the server's vulnerabilities

**Microsoft Baseline Security Analyzer (MBSA)**
- Microsoft Baseline Security Analyzer (MBSA) is a software tool released by Microsoft to determine the security state of a system by assessing missing security updates and less-secure security settings within Microsoft Windows, Windows components such as Internet Explorer, IIS web server, and products Microsoft SQL Server, and Microsoft Office macro settings.

**Secure Dyanmic DNS**
- Dynamic DNS lets client computers dynamically update their resource records in DNS. 
- With typical unsecured dynamic updates, any computer can create records on your DNS server which leaves you open to malicious activity. 
- To keep your DNS server secure, secure DNS makes it so that only members of an Active Directory domain can create records on the DNS server.  

## Security
- As has been made very clear, one of the biggest concerns of any organization is security. 
- To secure systems, it is necessary to configure a wide range of settings. Windows 10 includes more than 3,000 Group Policy settings and more than 1,800 settings for Internet Explorer. 
    - Many of these settings are security-related settings that must be managed within an organization. 
    - A *security baseline* is a collection of security settings.

- group policies are often used to make computer more secure
- use *security templates* to implement security settings quickly and efficiently, copy settings, check, etc.
- a *security template* is a collection of configuration settings stored in a text file with the .inf extension

## Using Security Compliance Manager
- free tool from Microsoft that can be used to quickly configure and manage your desktops, traditional data center, and private cloud using Group Policy and Sysmte Center Configuration Manager
- to install, .NET Framework 3.5 must be installed

## Using Security Baselines
- You can use security baselines to:
Ensure that user and device configuration settings are compliant with the baseline. 
- Set configuration settings. For example, you can use Group Policy, System Center Configuration Manager, or Microsoft Intune to configure a device with the setting values specified in the baseline.

- Removing users from the administrative role on computers can reduce the number of applications they can install, but it does not prevent them from loading apps that do not require administrative privileges to run. Use AppLocker to establish rules that determine which programs your users are allowed to run.

- *Universal Windows Platform* (UWP) apps are a special type of windows store app taht can be installed on multiple platforms
- *Windows Store for Business* supports purchases of Windows apps, options, re-use licenses
    - consider deployment of *Line of Business (LOB)* apps
-  LOB apps include apps that are critical to running the company business as well as apps that are unique to the company’s main business. 
- To use the new Windows Apps format for your LOB apps, deploy them via the Windows Store or a process called sideloading.
