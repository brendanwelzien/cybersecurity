# Authentication, Authorization, And Accounting

- *Nonrepudiation* prevents one party for denying actions they carry out

Type | Meaning
-----|-------
Authentication Based on what user knows | password, pin
Authentication Based on what user has | digital certificate, smart card (virtual too uses TPM chip), security token
Authentication based on what user is | biometrics, RADIUS (remote authenticatoin dial in user service), TACACS+(terminal access controller access-control system plus)

- radius and tacacs+ are protocols that provide security for computers to connect and use network service
    - resides on remote system
    - The server then authenticates a username/password combination (authentication), determine if a user is allowed to connect to the client (authorization), and log the connection (accounting). 

## Using RUNAS
- use standard non-admin user to perform most tasks
- admin tasks, use RUNAS command or built-in options that are included with Windows operating system

## Active Directory
- stores, organizes, and provides access to info
- created by Microsoft which provides variety of network services
- a *domain controller* is a Windows server that stores replica of acc info and defines domain boundaries, otherwise it is a *member server*

## Server Roles
- PDC Emulator, backwards compatibility for NT4 clients, acts as primary domain controller for password changes and acts as the master time server within domain
- **NTLM**, default authentication protocol for Windows NT, fall-back authentication if it cannot complete Kerberos authentication 
    - challenge-response mechanism
- **Kerberos**, security and authentication is based on secret key tech where every host on the network has its own secret key
    - domain controllers and clients must have the same time, Key Distribution Center has database of secret keys

## Organization Units
- organize objects within a domain and minimize the number of domains, use **organizational units**
    - delete admin control to any level of domain tree by using OU
- an **object** is assigned a unique 128-bit number referred to as Globally Unique Identifier (GUID)(similar to DNA or fingerprint)
- **accounts**:
    1. local user account (stored in security accounts manager)
    2. domain user accounts (stored on domain controller)
- **group**: collection of user or computer accounts
    - different from a container, the group does not store, just lists
    - simplifies administration, especially when assigning right and permissions
    1. security groups
    2. distribution groups
    ### Built-In Groups
    - Domain Admins
    - Domain Users
    - Account Operators
    - Backup Operators
    - Authenticated Users
    - Everyone
- **rights**: authorizes user to perform certain actions on a computer
- **permission**: defines type of access that is granted
    - to keep track of which user can access an obkect and what user can do is stored in **access control list (ACL)**
        1. Full control
        2. modify (change, but cannot create new ones)
        3. read and execute (read and run programs)
        4. read
        5. write (change, and create new files)
    - **NTFS**: file system used in today's operating system
        - permissions:
        1. explicit permission= permissions granted directly to file or folder
        2. inherited= permissions granted to a folder and its children objects
        - effective permissions: actual permissions when logging in and accessing a file or folder (consist of explicit + any inherited permissions)

## Admin Shares
- An administrative share is a shared folder typically used for administrative purposes and usually hidden. 
- To make any shared folder or drive hidden, the share name must have a $ at the end of it. 
- Because the share folder or drive cannot be seen during browsing, you have to use a UNC name to find the folder or drive, which includes the share name (including the $). 
- By default, all hard drive volumes with drive letters automatically have administrative shares (C$, D$, E$, and so on). 
- Other hidden shares can be created as needed for individual folders.
- the *registry* is a central database which stores all hardware configs, software, policies
    - HKEY_CLASSES_ROOT: Stores information about registered applications, such as file association that tells which default program opens a file with a certain extension.
    - HKEY_CURRENT_USER: Stores settings that are specific to the currently logged-on user. When a user logs off, the HKEY_CURRENT_USER is saved to HKEY_USERS.
    - HKEY_LOCAL_MACHINE: Stores settings that are specific to the local computer.
    - HKEY_USERS: Contains subkeys corresponding to the HKEY_CURRENT_USER keys for each user profile actively loaded on the machine.
    - HKEY_CURRENT_CONFIG: Contains information gathered at runtime. Information stored in this key is not permanently stored on disk, but rather regenerated at the boot time.

### Encryption
- encryption is process of converting data into a format that cannot be read by another user
- symmetric: single key to encrypt and decrypt data
    - initially you need to exchange the key between sender and receiver
- asymmetric: public key, uses two mathematically related keys for encryption
    - one key is used to encrypt while the second is used to decrypt
- forms of encryption:
    - Secure Sockets Layer (SSL)
    - Secure multipurpose Internet Mail Extension (S/   MIME)
    - Pretty Good Privacy (PGP)
    - Encrypting File System (EFS)
    - BitLocker
    - Virtual Private Network (VPN)


## Digital Certs and Sigs
- A digital certificate is an electronic document that contains a person’s or organization’s name, a serial number, expiration date, a copy of the certificate holder’s public key (used for encrypting messages and to create digital signatures) and the digital signature of the CA that assigned the digital certificate so that a recipient can verify that the certificate is real.
The most common digital certificate is the X.509 version 3. 
- A digital signature is a mathematical scheme that is used to demonstrate the authenticity of a digital message or document 

## Windows Biometric Framework
- enables users to manage device settings through control panel
- Windows Hello is a 10.0 version of biometric authentication 
= Microsoft Passport is a two-factor auth with enrolled device and biometric or pin
    - need microsoft account, azure active directory, or windows server 2016 active directory

## Summary
- AAA (Authentication, Authorization, and Accounting) is a model for access control. 
- Authentication is the process of identifying an individual. 
- After a user is authenticated, users can access network resources based on the user’s authorization. Authorization is the process of giving individuals access to system objects based on their identity.
- Accounting, also known as Auditing is the process of keeping track of a user's activity while accessing the network resources, including the amount of time spent in the network, the services accessed while there and the amount of data transferred during the session.
- When two or more authentication methods are used to authenticate someone, you are implementing a multifactor authentication system.
- The most common method of authentication with computers and networks is the password.
- Active Directory is a technology created by Microsoft that provides a variety of network services, including LDAP, Kerberos-based and single sign-on authentication, DNS-based naming and other network information and Central location for network administration and delegation of authority.
- A user account enables a user to log onto a computer and domain.]A right authorizes a user to perform certain actions on a computer such as logging on to a system interactively or backing up files and directories on a system. 
- A permission defines the type of access that is granted to an object (an object can be identified with a security identifier) or object attribute.
- Encryption is the process of converting data into a format that cannot be read by another .user. Once a user has encrypted a file, it automatically remains encrypted when the file is stored on disk
- Decryption is the process of converting data from encrypted format back to its original format.
- Encryption algorithms can be divided into three classes: Symmetric, Asymmetric, and Hash function.
- Symmetric encryption uses a single key to encrypt and decrypt data. Therefore, it is also referred to as secret-key, single-key, shared-key, and private-key encryption.
- Asymmetric encryption, also known as public key cryptography, uses two mathematically related keys. 
- One key is used to encrypt the data, while the second key is used to decrypt the data.
- Different from the symmetric and asymmetric algorithms, a hash function is meant as a one-way encryption. 
- This means that after it has been encrypted, it cannot be decrypted. =
- PKI is a system consisting of hardware, software, policies, and procedures that create, manage, distribute, use, store, and revoke digital certificates.
- The most common digital certificate is the X.509 version 3. 
- The certificate chain, also known as the certification path, is a list of certificates used to authenticate an entity. It begins with the certificate of the entity and ends with the root CA certificate.]A digital signature is a mathematical scheme that is used to demonstrate the authenticity of a digital message or document. It is also used to confirm that the message or document has not been modified. 
- When surfing the internet and needing to transmit private data over the internet, use SSL over HTTPS (https) to encrypt the data sent over the internet. By convention, URLs that require an SSL connection start with https: instead of http:
- IPsec is a suite of protocols that provide a mechanism for data integrity, authentication, and privacy for the Internet Protocol.
- VPN links two computers through a wide-area network, such as the internet. 
- Windows Hello is a Windows 10 biometric authentication system that uses a user’s face, iris, or fingerprint to unlock devices. 
- Syslog is a standard for logging program messages that can be accessed by devices that would not otherwise have a method for communications. 