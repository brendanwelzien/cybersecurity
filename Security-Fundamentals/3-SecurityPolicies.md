# Security Policies in Depth

## Password
- most of today's data protection is based on *password*
- component of a security program is that employees use *strong passwords* (length, complexity, and randomness)
- when an **account lockout occurs** Microsoft provides 3 settings:
    1. Account lockout duration
    2. Account lockout threshold
    3. Reset account lockout counter offer

**Password History**
- setting that determines # unique passwords that must be used before using a password used in the past
    - prevents user from using recycled passwords through a system
- time between password changes can be defined by *2* settings:
    1. minimum password age
    2. maximum password age

**Service Accounts**
- passwords should always *expire* unless under *unique* circumstances (**service accounts** for running apps)
- passwords that do not expire can be a serious security issues in virtually all environments

**Password Procedures**
- every organization should establish a *security policy*, a written document describing the security of the entity
    - include **an acceptable use policy**, describing constraints and practices that users must agree to in order to access the network, resources, and internet for the corporate
    - include **password policy**, describing password requirements and how often it should be changed

**Group Policy Object (GPO)**
- set of rules which an admin controls over config of active directory (user acc, operating systems, apps, etc.)
- GPOs used for centralized management and config of active directory environment

**Fine-grained password policies**:
- allow for specifying multiple password policies within a single domain so that different restrictions for password and account lockout policies can be applied to different sets of users in a domain

- enabling fine-grained password policies:
1. create **Password Settings Object** (PSO)
2. configure same settings that are configured for password and lockout policies
3. if a fine grained password is not defined server 2016 will use the **Default Domain Policy**

## Common Attack Methods for Passwords
- recognized as one of weak links in security programs
    - must rely on users in selection of passwords
    - strong passwords are still vulnerable to attack through variety of different mechanisms

**Dictionary and Brute Force**
- dictionary attack uses a dictionary containing extensive list of passwords that attacker tries with a user ID to guess the correct pasword
- brute force attack does not rely on lists of passwords, but tries all possible combos of permitted character types
- Microsoft has taken efforts to combat *malware* through developing *Device Guard* and *Credential Guard*

**Device Guard**
- hardens a computer system against malware by running on *trusted* apps preventing malicious code from running

**Credential Guard**
- hardens key system and user security information (available only through Windows 10 Enterprise)

- *BOTH* use *Windows 10 virtual secure mode (VSM)* which uses the processor's virtualization to protect the PC including data and credential tokens on the system's disks

**Physical Attacks**
- physical attacks can *completely* bypass almost *ALL SECURITY MECHANISMS* such as capturing passwords / other data directly from keyboard when software or hardware *keylogger* is used
- if your *encryption key* passes through the *keylogger*, your encrypted data may also be jeopardized

**Sniffers**
- software / sometimes hardware apps that capture network packets as they traverse a network, displaying them for the attacker
- sniffers are valid forms of test equipment, used to identify network and app issues, but the tech has been abused by attackers as a way to grab *logon credentials*