# Introduction

Security professionals must design and defend systems that protect data in transit and at rest using strong cryptographic methods. They must also implement technical countermeasures to protect complex system environments, including cloud and endpoint components.

# Scenario

FinSecure Corp. is preparing for a major expansion of its digital operations. The company is migrating several services to a new platform and increasing remote access for staff. As a security analyst, you have been asked to assess the organization's current data protection strategies and system architecture, including cryptographic protections, vulnerabilities, and countermeasures, to ensure they are resilient, compliant, and well defended.

# Assignment

A.  Using the attached “Data Security and Systems Defense Artifacts,” evaluate and recommend encryption strategies for the provided data protection scenario by doing the following:

1.  Identify two data protection vulnerabilities and risks (e.g., Risk = Vulnerability × Threat × Likelihood × Impact) related to either data in transit or data at rest, based on the provided scenario.

2.  Recommend a cryptographic method to mitigate each identified risk from part A1.

a.  Justify how each recommendation from part A2 supports data confidentiality or integrity.



B.  Analyze the system architecture diagram in the attached “Data Security and Systems Defense Artifacts” for security weaknesses by doing the following:

1.  Identify three technical vulnerabilities or design flaws relevant to the attached system architecture diagram (i.e., endpoints, virtual machines, or network components).

2.  Recommend a countermeasure for each vulnerability identified in part B1 based on applicable best practices (e.g., hardening, segmentation, endpoint detection).

a.  Explain how each countermeasure from part B2 mitigates the associated vulnerabilities from part B1 and improves the system’s overall security.

 

C.  Using the information in the operational environment summary in the attached “Data Security and Systems Defense Artifacts,” evaluate the system’s overall security posture by doing the following:

1.  Propose two tools or configurations to improve the system's resilience, that is, its ability to detect, respond to, and recover from threats.

2.  Explain how each proposed tool or configuration from part C1 improves the organization's ability to detect, respond to, or recover from threats. Include a justification for each proposal.

 

D.  Acknowledge sources, using in-text citations and references, for content that is quoted, paraphrased, or summarized.

 

E.  Demonstrate professional communication in the content and presentation of your submission.

# My Essay

[C845 Assignment 3 (1) (1).pdf](https://github.com/user-attachments/files/26762996/C845.Assignment.3.1.1.pdf)

FinSecure’s HR and Finance departments transmit payroll and employee data over
an internal FTP server using legacy file transfer protocols. FTP transmits data, including
credentials and file contents, entirely in plaintext. Meaning the attacker with access to the
internal network can intercept and read that traffic through passive sniffing or a man-inthe-middle attack. Compounding this, the organization’s HTTP connections to third-party
partners are configured to allow multiple TLS versions, including TLS 1.0. This has been
formally deprecated by the PCI DSS standard and is known to be vulnerable to attacks such
as Browser Exploit Against SSL/TLS and Padding Oracle On Downgraded Legacy
Encryption. A client or server that negotiates down to TLS 1.0 during a handshake can
expose sensitive financial data to decryption by an adversary capable of intercepting the
session.

Factor / Assessment
Vulnerability FTP (no encryption) + TLS 1.0 permitted
(weak encryption)
Threat Internal network interception
(eavesdropping/MITM) & external
downgrade attacks on partner connections
Likelihood High, internal actors or compromised
devices can passively sniff FTP without any
special tools, TLS downgrade attacks are
well-documented and actively exploited
Impact High, payroll data employee PII, and
customer financial data are directly
exposed, triggering GLBA, PCI DSS, and
state level privacy violations

Risk level is high. The combination of an unencrypted internal protocol and a
deprecated external encryption standard creates substantial exposure for both employee
and customer data, with a high probability of exploitation and severe regulatory
consequences. 

Vulnerability two is customer PII and financial records stored in clear text at rest.
The on-premises finance server stores customer PII and financial records in a relational
database, with data written to disk in clear text. Additionally, the off-site backup storage
repository retains uploaded files in their existing format without server-side or automatic
encryption, and application encryption keys are stored in configuration files on the same
servers as the applications they protect. This is a critical data-at-rest vulnerability. If an
attacker gains physical or logical access to the finance server, the database, or the off-site
backup repository. They will have immediate access to all stored records. Also, collocating
encryption keys with the data they are meant to protect entirely defeats the purpose of
encryption. A key stored alongside its ciphertext effectively makes the encryption
transparent.

Factor / Assessment
Vulnerability Cleartext database storage, unencrypted
offsite backups, co-located encryption
keys
Threat Unauthorized access via cerd theft, insider
threat, physical access to storage media,
or lateral movement post breach
Likelihood High, annual password changes, no MFA,
quarterly patching cycles, and 90 day
backup retention with standard
permissions all increase the window of
exposure, the offsite repository is
accessible by multiple departments
Impact Critical, direct exposure of customer PII
and financial records constitute a breach
under GLBA, PCI DD, and state laws

Risk level critical. Storing sensitive financial records in cleartext with co-located
keys, combined with unencrypted offsite backups and weak access controls, creates an
environment where a single successful intrusion will yield immediate access to sensitive
data.

For internal file transfers, FinSecure should immediately decommission the legacy
FTP server and replace it with SFTP (Secure File Transfer Protocol). SFTP operates over SSH
(Secure Shell), using strong asymmetric key exchange, such as ECDH with Curve25519.
And during session establishment and symmetric encryption, such as AES-256-CTR or
AES-256-GCM for the data channel. Every byte of the payroll and employee data transfer,
including the credentials, is cryptographically protected from the moment the connection
is initiated. SFTP simplifies firewall rules by using a single port, reducing the attack surface. 

For external HTTPS connections to third-party partners, FinSecure should enforce
TLS 1.3 at a minimum and only accept TLS 1.3, disabling TLS 1.0, 1.1, and 1.2 on all
relevant endpoints. TLS 1.3 eliminates the entire class of downgrading negotiation attacks.
By removing support for legacy cipher suites. Mandating forward secrecy via Diffie-Hellman
key exchange and reducing the handshake to fewer round trips, thereby shrinking the
window of exposure during the connection. All TLS 1.3 cipher suites provide authenticated
encryption with associated data, ensuring confidentiality and integrity.

For confidentiality, SFTP’s AES-256 symmetric encryption ensures that payroll and
employee data traversing the internal network is rendered unintelligible to any party that
intercepts the network traffic without the session key. TLS 1.3’s mandatory use of AEAD
cipher suites similarly ensures that financial data exchanged with third-party partners
cannot be read by an intercepting party. The forward secrecy property of TLS 1.3 further
ensures that even if a long-term private key is later compromised, previously recorded
sessions cannot be retroactively decrypted. A critical protection for sensitive data that may
be targeted for long-term storage. For integrity, SSH’s cryptographic message
authentication (built into SFTP sessions via HMAC or AEAD) guarantees that data arriving at
the destination is byte-for-byte identical to what was sent. Detecting any tampering or
corruption in transit. TLS 1.3’s AEAD construction provides the same guarantee for partner
connections; any modification, whether by a network attacker or a compromised
middleman, causes authentication to fail, and the session is terminated before tampered
data is accepted. This directly supports FinSecure’s obligation to ensure the integrity of
financial records as required under GLBA and PCI DSS.

Recommendation for vulnerability two would be to implement AES-256 encryption
at rest with a dedicated key management system. At the database level, FinSecure should
configure transparent data encryption (TDE). TDE encrypts the underlying data files, logs,
and backups automatically at the storage layer. This way, any access to the disk yields only
ciphertext. Decryption occurs only when data is accessed via the authenticated database
engine, preserving normal application functionality while eliminating cleartext exposure at
rest. Next is encryption of offsite backup files, using AES-256 prior to or at the time of
upload, rather than relying on the repository to handle encryption. This ensures that the
backup files themselves are ciphertext, regardless of the repository's access controls.
FinSecure must also decouple encryption keys from the data and systems by deploying a
hardware security module (HSM) or a dedicated key management system (KMS).
Encryption keys must never reside in configuration files on the same server. The HMS/KMS
provides a hardened access-controlled vault for key storage, enforces key rotation policies,
and maintains an audit trail. This addresses not only the cryptographic vulnerability but
also the access control and auditability gaps identified in FinSecure’s current key
management practices.

For confidentiality, AES-256 is a symmetric block cipher standardized by NIST and
considered almost impossible to brute-force with current technology. Applying TDE to the
finance database ensures that customer PII and financial records are never present on disk
in a readable form. Encrypting backup files before off-site transfer ensures that the
unencrypted off-site repository cannot be exploited as a secondary pathway to clear text
data. Integrity is maintained when AES is implemented in an authenticated mode, such as
AES-256-GCM, the cipher provides both encryption and a cryptographic authentication
tag. Any unauthorized modification of the stored ciphertext causes the authentication tag
verification to fail upon decryption, alerting the system to tampering before the data is
used. Proper key management through an HSM/KMS further strengthens integrity by
ensuring that key access is auditable, rotation is enforced, and no single actor can silently
access or modify keys without generating a logged event.


The first vulnerability identified in the architecture diagram is a single network
gateway, which creates a critical point of failure and exposes the network to flat exposure.
The diagram describes the data center's core business systems, application servers, web
servers, and database servers. All connected through a single network gateway. Network
traffic is then routed through a perimeter firewall and internal switch before reaching
department subnets. The first part of this vulnerability is that the reliance on a single
gateway means that if it were compromised for whatever reason, DDoS, or simply fails, the
entire data center becomes unreachable. No redundant path, failover device, or secondary
gateway is described. The second part is the flat or minimally segmented network topology,
which means that once an attacker breaches the perimeter firewall, they can achieve
broad lateral movement. The database servers, which store customer PII and financial
records, sit on the same internal network as the applications and we servers, with no
described internal segmentation. This is dangerous given the scenario, which describes
remote employees connecting via a VPN configured for split tunneling, allowing them to
connect to the corporate network and the open internet. A malware-infected remote
endpoint could serve as a breach head for lateral movement into the flat network once the
VPN is established.

Vulnerability two is the VPN gateway’s architectural placement and split tunneling
configuration. The diagram shows the VPN gateway linking remote employees directly into
the corporate network via an IPSec connection, with no described intermediate quarantine
or remote access zone between the VPN termination point and internal resources. The
scenario confirms that the VPN is configured for split tunneling, allowing remote
employees to simultaneously maintain an active connection to the corporate network and
brose the open internet. This is a significant architectural design flaw at the network level. A
remote endpoint that is infected with malware or compromised while connecting to the
internet can, through an active VPN tunnel, serve as a direct bridge into the corporate
network. Because the VPN terminates inside the corporate network rather than into an
isolated segment requiring further authentication, a compromised remote machine
inherits broad internal network access the moment the tunnel is established. The flat
internal network, already identified in vulnerability one, compounds this risk. Once inside
the VPN, the remote endpoint or the attacker controlling it faces no internal segmentation
barriers between the subnets and data center systems. 

Vulnerability three is the absence of any internal firewall or segmentation boundary
between the corporate network and the data center. The diagram routes all traffic through a
single perimeter firewall and internal switch before reaching departmental subnets.
However no internal firewall or access control boundary is described between the
corporate network subnets, where HR and IT users operate, and the data center tier, which
hosts the application, web, and database servers. This means that any user or
compromised host operating within the corp network has a potential direct network path to
the data center’s core systems including PII and financial records. The architecture
provides no mechanism to enforce least privilege access at the network layer. This is a
structural design flaw that relies entirely on the perimeter firewall, providing no defense-indepth once the boundary is crossed.

The countermeasure for the first vulnerability is to implement network segmentation
with defense-in-depth zones and redundant gateway architecture. FinSecure should
redesign its network architecture to implement defense-in-depth through segmentation,
replacing the flat, single-gateway topology with a tiered zone model that enforces the
principle of least privilege at the network layer. This means establishing at a minimum three
security zones with enforcement between them. A demilitarized zone (DMZ) housing webfacing servers and any service that must be reachable from external networks or third-party
partners, isolated from internal systems by a dedicated internal firewall or NGFW policy. An
application tier containing application servers, accessible from the DMZ only on specific
required ports and protocols, with all other traffic denied by default. A data tier containing
database servers and data storage, accessible only from the application tier on explicitly
permitted database ports, completely inaccessible from the DMZ or any external-facing
segment. Interzone traffic should be enforced through stateful firewall rules of NGFW
policies with application layer inspection, and the HR and IT subnets should be segmented
from each other, and from the data center tiers using VLANs with inter VLAN routing
controlled by access control lists. The VPN gateway should terminate remote connections
into a dedicated quarantine or remote access zone. Rather than directly into the corporate
network. Further authentication and authorization are required to access internal
resources. Additionally, the single gateway should be replaced with a redundant gateway
pair in an active-passive or active-active high-availability configuration. Ensuring that a
single loss device does not sever the connection to the data center. Split tunneling on the
VPN should be disabled, forcing all employees' traffic to pass through the corporate
security stack before reaching the internet or returning to internal resources.

These countermeasures mitigate vulnerability one and improve overall security, with
network segmentation directly eliminating the lateral movement that the flat architecture
enabled. By placing the database in an isolated segment with no direct inbound
connectivity from the web-facing DMZ, a successful compromise of a web server no longer
provides a direct network path to customer PII and financial records. The attacker must
defeat additional controls. The inter-zone firewall complicates the attack, causing every
tier attempt to penetrate, dramatically increasing the cost and complexity of the breach.
And increases the likelihood that malicious traffic will be detected before it reaches highvalue targets. Redundant gateways directly address the availability risk, ensuring
FinSecure’s expansion plans are not built on a single point of failure. Disabling split
tunneling eliminates the breach head risk posed by remote endpoints that are
simultaneously exposed to the internet and VPN connections. Ensuring the compromised
remote machine cannot serve as a direct bridge between the threat actor and FinSecure’s
internal network. These changes transform this network from being a perimeter-only
model, where a single firewall bypass grants internal access. Into a layered architecture
where each tier must be independently defeated, substantially improving FinSecure’s
resilience both to external and insider threats.

The countermeasure for vulnerability two is to reconfigure the VPN architecture to
terminate remote connections into a dedicated remote access zone, or quarantine
segment, rather than directly into the corporate network, and to disable split tunneling
entirely. The VPN gateway should be repositioned so that remote employees land in the
quarantined zone, from that zone, access to internal recourses. There resources must be
explicitly granted through firewall policy based on user role and least privilege. Requiring
additional authentication before any internal resource is reachable. Split tunneling must be
disabled to allow both the internet and internal resources pass through FinSecure’s
security stack. This ensures that web based threats encountered during internet browsing
cannot reach VPN tunnel and that all outbound and inbound traffic is subject to inspection.

Repositioning VPN termination into a quarantined zone directly eliminated the
architectural flaw that allowed remote endpoints to achieve broad internal network access
the moment a tunnel was established. By requiring explicit, role-based firewall policy to be
satisfied before any internal resource is reachable from remote access zone, a
compromised endpoint no longer serves as a direct bridge into corporate network. The
attacker controlling a compromised remote machine is stopped at the quarantine zone
must defeat additional access controls. By disabling split tunnelling it closes the
simultaneous connections, ensuring all traffic is subject to inspections, and they cant
bridge into internal networks.

Countermeasure for vulnerability three is to deploy an internal firewall or next
generation firewall (NGFW) between the corporate network and the datacenter, enforcing
explicit access control policies between user facing subnets and data center resources.
This internal boundary firewall should be configured with deny-by-default rules, permitting
only explicitly defined, role-based traffic flows between the HR and IT subnets and the
specific applications they require. No direct connectivity should be permitted from any
corporate subnet to the database tier. All interzone traffic should be inspected at the
application layer using NGFW deep packet inspection, with logging of all connection
attempts forwarded to centralized monitoring platform.

Deploying an internal firewall between the corporate network and the data center
directly address the structural absence of any access control boundary. The deny-bydefault policy ensures that even an attacker who has successfully coprimised a host within
the corporate network cannot freely reach the database servers without being blocked and
logged at the internal boundary. NGFW application leyer inspection adds the ability to
detect and block malicious traffic patterns that would otherwise traverse the internal
network undetected. This converts the current perimeter only model, into a layered
architecture where the corporate data center boundary is independently enforced,
substantially reducing the blast radius of any internal compromise and directly supporting
FinSecure’s regulatory obligations under GLBA and PCI DSS.

First tool to improve the systems resilience is to deploy an Endpoint Detection and
Response (EDR) solution across all endpoints, servers, and VMs. Replacing the current
standalone antivirus model. Unlike traditional antivirus software, which relies on signaturebased detection and generates alerts only locally. EDR continuously monitors endpoint
behavior in real time, detecting anomalous activity patterns. And forwards all telemetry to
a centralized management console. EDR also provides active response capabilities,
isolating a compromised endpoint from the network, terminating malicious processes, or
rolling back the root system changes, without requiring physical or manual intervention on
the affected machine.

The second tool FinSecure should deploy is automated, immutable backups using a
solution that enforces encryption of all backup data at the time of creation (using AES-256).
Storing backups in a write-once, read-many (WORM) format prevents modification or
deletion for a defined retention period. And automated recovery testing on a monthly
schedule rather than the current annual test. Backup jobs should generate automated
verification reports confirming both successful completion and encryption status. With
alerts triggered immediately on any backup failure, rather than relying on the next
morning's manual review.

EDR helps with detection with its behavioral monitoring. Where the current posture
generates silent local alerts. EDR streams endpoint telemetry continuously to a central
server, enabling security staff to detect credential abuse and other anomalies. Rather than
discovering it reactively. Behavior detection also detects threats with no known signature.
Response is improved with EDR’s active response capabilities address FinSecure’s current
incident response weaknesses, where IT staff coordinates responses only after issues are
reported. EDR allows a security analyst to remotely isolate a compromised endpoint within
seconds of detection, containing the threat before the breach. Justification comes from
FinSecure’s expanding remote workforce, which is increasing the number of endpoints
connecting to internal resources via VPN. Deploying EDR is a foundational requirement for
maintaining visibility and control over that expanding endpoint landscape. It directly
supports compliance with GLBA’s safeguarding rule.


Immutable backups help with recovery because the current backup configuration
leaves FinSecure poorly positioned to recover from an attack or data destruction event.
Immutable backups stored in WORM format cannot be encrypted or deleted by
ransomware. Monthly automated recovery tests verify that the backup data is actually
restorable and uncorrupted before a real incident occurs. Automated failure alerting
ensures that a failed backup is known and addressed the same day, rather than being
discovered after an incident when the backup is ended. Justification is that since the
organization handles financial services, these companies are the most frequently targeted
sectors for ransomware. A verified, encrypted, immutable backup ensures FinSecure can
recover its data without having to negotiate with the attacker.

Reference List
Cybersecurity and Infrastructure Security Agency. (2023). Ransomware guide. U.S.
Department of Homeland Security. https://www.cisa.gov/resourcestools/resources/ransomware-guide

Dworkin, M. (2007). Recommendation for block cipher modes of operation: Galois/Counter
Mode (GCM) and GMAC (NIST Special Publication 800-38D). National Institute of
Standards and Technology. https://doi.org/10.6028/NIST.SP.800-38D

Dworkin, M., Barker, E., Nechvatal, J., Foti, J., Bassham, L., Roback, E., & Dray, J. (2001).
Advanced Encryption Standard (AES) (FIPS Publication 197). National Institute of
Standards and Technology. https://doi.org/10.6028/NIST.FIPS.197

Federal Trade Commission. (2023). Standards for safeguarding customer information (16
C.F.R. Part 314). https://www.ftc.gov/legal-library/browse/rules/safeguards-rule

Kent, K., & Souppaya, M. (2006). Guide to computer security log management (NIST Special
Publication 800-92). National Institute of Standards and Technology.
https://doi.org/10.6028/NIST.SP.800-92

National Institute of Standards and Technology. (2020). Security and privacy controls for
information systems and organizations (NIST Special Publication 800-53, Rev. 5).
https://doi.org/10.6028/NIST.SP.800-53r5

PCI Security Standards Council. (2022). Payment Card Industry Data Security Standard
(PCI DSS) v4.0. https://www.pcisecuritystandards.org

Rescorla, E. (2018). The Transport Layer Security (TLS) protocol version 1.3 (RFC 8446).
Internet Engineering Task Force. https://doi.org/10.17487/RFC8446

Scarfone, K., & Souppaya, M. (2016). Guide to enterprise telework, remote access, and
bring your own device (BYOD) security (NIST Special Publication 800-46, Rev. 2). National
Institute of Standards and Technology. https://doi.org/10.6028/NIST.SP.800-46r2




