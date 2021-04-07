# Security

- what are you trying to protect
- why does it need to be protected
- what you are protecting it from

**CIA**

- confidentiality
- integrity
- availability

**Confidentiality**

- ensuring access is restricted to only permitted users, apps, or computer systems
- dels with keeping information networks, and systems secure from unauthorized access
  - encryption, authentication, access controls

**Integrity**

- consistency, accuracy, and validity of data or information
- a successful security program is to ensure the data is protected against unauthorized or accidental changes

**Availabiity**

- resource accessible to a user, app, or computer system when required
  - availability threats = accidental and deliberate

**Risk Management**

- in a risk assessment environment it is common to record risks in a _*isk register* (documentation of risks, impacts, controls, and other info required by RM program)

**Dealing with Risks**

- responses to the risks you have chosen...
  - avoidance
  - acceptance
  - mitigation
  - transfer
- residual risk: the risk of an event occurring even after measures have been taken to reduce likelihood

## Threat Modeling

1. Identify assets
2. create an architecture overview
3. decompose the security components and applications
4. identify threats
5. document threats
6. rate threats

## STRIDE (mnemonic device for security threats)

- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

## DREAD (mnemonic device for ranking risk)

- Damange potential
- Reproducibility
- Exploitability
- Affected Users
- Discoverability

**Least Privilege Principle**

- giving a certain user, system, or app no more privilege that it needs to perform function or job (basically do not give someone master control of everything)
  - groups
  - multiple user accounts for adminisstrators
  - third party apps
  - processes and procedures
- follows the idea of *separation of duties* which prevents an entity from having full access
    - prevents fraud, theft, and errors

    **Attack Surface**
    - set of methods and avenues and attacker can use to enter a system and potentially cause damage
    - the larger the attack surface, the greater risk of a successful attack
    - **Ingress traffic** is traffic that comes from outside the network's routers and proceeds toward a destination inside the network
    - **Egress traffic** is traffic begins inside a network and proceeeds through its routers to desintation outside of network

**Social Engineering**
- method used to access data, systems, or networks mainoy through **misrepresentation**
- relies on trusting nature of the person being attacked

## Security and Cost
- security costs $$$
- strive to make security measures as seamless as possible to authorized users who are accessing confidential information
- if security becomes a heavy burden, users will find other methods to work around measures established
- training goes a long way in protecting your information because it shows users what warning signs to look for
1. physical security is the first line of defense
    - understanding site security, computer security, removable devices and drives, access control, keyloggers, etc.
    - goals:
        1. **Authentication**
        2. **Access Control**
        3. **Auditing** (recording activities, reviewing)

## Physical Premises
- external perimeter (first line of defense surrounding your office)
    - parking lot lights, guard, gate, cameras
- internal perimeter (building walls, doors, locks, smoke detectors)
- secure areas (limit external attackers and internal employee access = badge readers, x-ray scanners, etc.)

## Computer Security
- processes, procedures, policies, and tech used to protect servers, desktop computers, and mobile computers

## Removable Devices
- 3 security issues associated with removable storage:
    - loss
    - theft
    - espionage
- keylogger: device that captures keystrokes
    - attacker can place a device between keyboard and computer or install a software program to record each keystroke taken and replays data to capture critical information

## Summary
- Before you can start securing your environment, you need to have a fundamental understanding of the standard concepts of security. 
- CIA, short for confidentiality, integrity, and availability, represents the core goals of an information security program.
- Confidentiality deals with keeping information, networks, and systems secure from unauthorized access. 
- One of the goals of a successful information security program is to ensure integrity, or that information is protected against any unauthorized or accidental changes.
- Availability is defined as the characteristic of a resource being accessible to a user, application, or computer system when required.
- Threat and risk management is the process of identifying, assessing, and prioritizing threats and risks. 
- A risk is generally defined as the probability that an event will occur. 
- Once you have prioritized your risks, there are four generally accepted responses to these risks: avoidance, acceptance, mitigation, and transfer.
- The principle of least privilege is a security discipline that requires that a user, system, or application be given no more privilege than necessary to perform its function or job.
- An attack surface consists of the set of methods and avenues an attacker can use to enter a system and potentially cause damage. The larger the attack surface of an environment, the greater the risk of a successful attack. 
- The key to thwarting a social engineering attack is employee awareness. If your employees know what to look out for, an attacker will find little success.
- Physical security uses a defense in depth or layered security approach that controls who can physically access an organization’s resources.
- Physical premises can be divided into three logical areas: the external perimeter, the internal perimeter, and secure areas.
- Computer security consists of the processes, procedures, policies, and technologies used to protect computer systems.
- Mobile devices and mobile storage devices are among the biggest challenges facing many security professionals today because of their size and portability.
- A keylogger is a physical or logical device used to capture keystrokes. 
- Threat modeling is a procedure for optimizing network security by identifying vulnerabilities, identifying their risks, and defining countermeasures to prevent or mitigate the effects of the threats to the system. 