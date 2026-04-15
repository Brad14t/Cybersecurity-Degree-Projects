# Introduction

Organizations face ongoing threats that require well-defined procedures for detection, response, and recovery. Security professionals must evaluate incident response plans for effectiveness and resilience and ensure network configurations are secure and optimized to prevent and mitigate attacks.

# Scenario

You are working as a cybersecurity analyst at FinSecure Corp, a midsize financial organization. A recent malware incident has prompted a comprehensive review of the company's incident response procedures and network security architecture. FinSecure operates primarily in an on-premises environment with some remote users connecting via VPN. As part of this review, you have been asked to evaluate how the incident was handled, assess the network architecture for vulnerabilities, and recommend adjustments to firewall and intrusion detection system (IDS) configurations to prevent future threats.

# Assignment

A.  Evaluate the organization's response to the security incident by doing the following:

1.  Identify three actions the organization took in response to the incident.

2.  Evaluate the effectiveness of each of the three actions from part A1 using a recognized incident response framework (e.g., NIST, SANS, ISO).

3.  Recommend two improvements to the organization’s incident response procedure that would strengthen detection, containment, or recovery efforts in future incidents, and justify why each recommendation would improve the organization’s incident response effectiveness.

 

B.  Analyze the provided network architecture diagram and firewall configuration by doing the following:

1.  Identify three vulnerabilities, design flaws, or misconfigurations that create or enable security risks in the network setup.

2.  Recommend a secure network design or remediation strategy for each of the three identified issues in part B1, and justify why each recommendation would improve network security.

3.  Explain how each recommendation in part B2 would improve the network's ability to resist or detect threats and support the confidentiality, integrity, or availability (CIA) of information.

 

C.  Review the existing firewall and IDS rule sets by doing the following:

1.  Identify two weaknesses or gaps in the existing firewall or IDS rule sets that create or could allow security risks.

2.  Explain how each weakness or gap identified in part C1 could allow known threats to exploit the network. Support your explanation with evidence from the provided artifacts.

3.  Propose two updated or additional firewall or IDS rules to address the weaknesses identified in part C1, and justify how each proposed rule would improve network security and help defend against the threats discussed in part C2.

 

D.  Acknowledge sources, using in-text citations and references, for content that is quoted, paraphrased, or summarized.

 

E.  Demonstrate professional communication in the content and presentation of your submission.

# My Essay

[C845 Assignment 2 (1).pdf](https://github.com/user-attachments/files/26760668/C845.Assignment.2.1.pdf)

The first notable action was isolating the compromised endpoint. After the IDS
flagged unusual outbound traffic at 09:52, the affected machine at IP address 10.1.1.45
was isolated from the network at 10:07, about 15 minutes after the alert was generated. “In
the NIST framework’s containment phase, prompt isolation of a compromised host is a
critical step to prevent the spread of malware and to stop command-and-control (C2)
communication.” (Cichonski, 2012) In this case, the IDS log reveals that lateral movement
via SMB to 10.1.2.10 was already occurring by 10:45, well after isolation was supposed to
take place. This raises serious questions about the completeness of containment. While
the action of isolating the machine was appropriate and aligned with NIST guidance, its
effectiveness was undermined by the fact that network segmentation was insufficient to
prevent the malware from reaching other internal hosts. The isolation of a single endpoint,
without broader subnet-level controls, left a window for further compromise. The action
earned partial credit for following the correct procedural step, but the outcome reveals that
the containment strategy lacked the depth necessary to be fully effective. 

The second action involved deploying antivirus and antimalware tools to eradicate
the threat, followed by restoring the affected system from backup. According to the
incident timeline, the endpoint was restored from backup at 13:45 on June 24. And AV
definitions were updated across all endpoints the following morning. Under NIST’s
eradication and recovery phases, this approach is consistent with best practices.
Removing malicious artifacts and restoring well-known system states are essential steps
before returning systems to operation. With the system restored the same day, operational
efficiency is achieved. However, a significant concern is that the IDS continued to generate
alerts involving the same source IP (10.1.1.45) as late as 08:02 on June 25th, when a
suspicious DNS query to a known malicious domain was logged. This post-restoration
activity suggests that either the backup used for recovery was compromised, the malware
had persisted in another location on the network, or eradication was incomplete. NIST
guidance emphasizes confirming that all traces of the threat are removed before recovery.

The third action was the organization-wide update of antivirus definitions,
completed on the morning of June 25th. From a NIST framework perspective, this action
falls within the eradication phase and represents a reasonable effort to improve baseline
defenses following the incident. “Updating the endpoint protection tool ensures that other
machines on the network are better equipped to detect and block variants of the GhostX
RAT.” (CISA, 2023) Applying updates network-wide rather than only to the affected machine
reflects an appropriate understanding that a single compromised host may indicate
broader exposure. The updates occurred more than 22 hours after the initial infection; a
more mature security posture would have triggered emergency definition updates
immediately upon malware detection. Rather than the next day, take remediation steps.
Additionally, antivirus software alone is insufficient against sophisticated RATs, which
evade signature-based detections. The action was reactive rather than proactive.

The first recommended improvement is implementing a formal, automated
containment playbook that includes network segmentation and subnet isolation, rather
than just single-host disconnection. The current procedure relies on manually disabling a
network port after an alert is escalated to on-call IT staff. This introduces human latency
into the containment process and, as seen in this incident, allows time for lateral
movement. By integrating the IDS with network access control or firewall automation, the
organization could trigger automated quarantine of the affected host and C2 traffic. “NIST
SP 800-61 recommends that organizations develop pre-approved containment strategies
that can be executed rapidly without requiring multi-step human approval chains.”
(Cichonski, 2012) Automating isolation would dramatically reduce the window between
detection and containment. 

The second recommendation is to establish a mandatory post-incident review
process for all security incidents. The current procedure only schedules a debrief if a threat
affects multiple departments. Under the NIST framework’s post-incident activity phase,
every incident, no matter how contained. Should be reviewed to identify root causes,
evaluate the effectiveness of the response, and generate documented corrective actions. A
lesson-learned culture is one of the most cost-effective defenses an organization can
invest in. Had a post-incident review been mandated earlier, the overly permissive firewall
rules and the lack of network segmentation that enabled lateral movement might have
been identified and addressed before this incident occurred.

The first vulnerability is an overly permissive inbound rule that allows any external
traffic to reach internal networks. Firewall rule 102 permits any source to reach internal
networks on any port and any service. This is a way too broad a rule, which neutralizes the
firewall as a boundary control. In a financial organization like FineSecure Corp, internal
networks should never be directly accessible from external sources without explicit
justification. This rule alone creates a wide attack surface, enabling port scanning,
exploitation attempts, and unauthorized internet access without any filtering. The IDS log
corroborates this risk, on June 24 at 10:14, and an external host at 162.155.10.102 was
observed scanning the internal subnet at 10.1.2.4. Which firewall rule 102 did nothing to
prevent or block.

The remediation for this vulnerability is to replace rule 102 with an explicit deny all
inbound rule for traffic originating outside the organization. Followed by a narrowly scoped
allow list of only the specific ports and protocols required for legitimate business
operations. All other inbound traffic should be denied by default, consistent with the
principle of least privilege. This approach transforms the firewall from a pass-through
device to a genuine enforcement boundary. It directly enhances confidentiality by
preventing internal resources from being exposed to unauthorized external parties. It also
supports availability by reducing organizations' exposure to denial-of-service and
exploitation attempts that could degrade critical systems.

Vulnerability two is the unrestricted outbound traffic from internal networks. Rule
103 permits all internal hosts to communicate with any external destination on any port.
While outbound rules receive less scrutiny than inbound rules, unrestricted outbound
traffic is well documented as an enabler of malware activity. Particularly for RATs and other
command-and-control frameworks that rely on outbound channels to communicate with
the attacker. In this incident, the GhostX RAT installed on the HR workstation established
C2 communication to the external IP 45.33.122.88 without any firewall interference. The
IDS detected the traffic, but the firewall permitted it. Additionally, the DNS query logged on
June 25, originating from the same internal host and directed at a known malicious domain,
also passed through the firewall unchallenged.


The recommendation is to implement egress filtering that restricts outbound traffic
only to approved destinations and necessary protocols. At a minimum, outbound
connections should be limited to explicitly permitted services such as HTTPS on port 443,
DNS on port 53 directed only to approved resolvers, and SMTP through the designated
email relay. All other outbound traffic should be denied and logged. For environments like
FinSecure where remote access is required, VPN enforced split tunneling with centralized
egress inspection should be highly considered. This would have directly interrupted GhostX
RAT’s ability to contact the home network, potentially preventing data exfiltration. From a
CIA perspective, egress filtering most directly serves confidentiality. It prevents internal
data from leaving the network. It also supports integrity by limiting the attacker’s ability to
receive instructions that could further corrupt or manipulate internal systems. 

Vulnerability three is the absence of network segmentation. The network
architecture, as described, lacks meaningful segmentation between critical systems. The
HR subnet, where the initial infection occurred, appears to have had unrestricted access to
other internal subnets, as evidenced by the IDS alert at 10:45 showing lateral movement
from 10.1.1.45 to 10.1.2.10 via SMB. In a well-segmented network, a compromised
workstation in the HR department should be unable to initiate SMB connections to hosts
on a separate subnet. The flat network topology at FinSecure allowed what began as a
single infected endpoint to become a multi host indient within hours. Rule 104 exposes the
firewall management console on port 8080 to any source, meaning an attacker who had
already established a presence on the internal network could potentially attempt to access
firewall rules.

The recommended remediation is a comprehensive network segmentation strategy
using VLANs and internal firewall policies or access control lists to enforce strict inter-zone
traffic rules. “Each department should reside in its own network segment with explicit,
minimal inter-segment communication rules.” (NIST, 2020) The firewall management
console should be accessible only from a dedicated, isolated management VLAN. And rule
104 should be replaced with a rule that restricts console access to only a specific
administrative IP range. SMB traffic should be blocked entirely between workstation
subnets. This change would have contained the incident, preventing lateral movement.
From a CIA perspective, segmentation strengthens all three pillars. It protects
confidentiality by ensuring that sensitive data cannot be accessed from compromised
machines. It protects integrity by limiting an attacker's ability to modify data or systems
outside their initial footprint. And it supports availability by containing incidents so that
critical systems remain operational even when one segment is under attack.


Weakness one is the absence of a firewall rule blocking command-and-control
traffic. The existing firewall rule set contains no mechanism to block, inspect, or flag
outbound connections from internal hosts to external IP addresses associated with
malicious activity. Rule 103, which permits all outbound connections, created the
conditions under which the GhostX RAT could operate without a firewall interface. The IDS
detected C2 communication at 09:50 on June 24. Traffic originated from internal host
10.1.1.45 and was directed toward external IP 45.33.122.88. But the firewall had no
corresponding rule to act on that information. Compounding this gap, a suspicious DNS
query from the same internal host to a known malicious domain was logged at 08:02 on
June 25, indicating that C2 or reconnaissance activity may have continued even after the
endpoint was restored. Because the firewall placed no restrictions on where internal hosts
could direct DNS queries, the malware had a persistent, unobstructed channel. Once
GhostX is installed in an endpoint, these tools do not require inbound connections; they
initiate outbound connections. An attacker controlling the C2 server simply waits for the
implant to check in, at which point they can issue commands, exfiltrate data, or expand
their foothold. Because rule 103 allowed all outbound traffic, the RAT had an open path to
its operator from the moment it was installed. The 38-minute gap between malware
installation at 09:14 and IDS detection at 09:50 represents a window during which data
exfiltration or system reconnaissance could have occurred silently, with the firewall
offering no resistance.

The proposed rule to address this weakness is to add an egress filtering rule that
denies all outbound traffic to destination IPs or domains not on the approved allowlist,
combined with a companion IDS rule that generates a high-priority alert whenever an
internal host initiates connections to known threat intelligence. Including known C2 IP
ranges and malicious domains. At the firewall level, this can be implemented as a deny rule
above rule 103 that references a regularly updated threat intelligence blocklist, with DNS
resolution restricted to internal or organizationally approved resolvers. Blocking the ability
of any host to resolve malicious domains through outbound DNS query resolvers. Blocking
the ability of any host to resolve malicious domains through external DNS services like
8.8.8.8 without authorization. At the IDS level, a signature rule should be configured to alert
and trigger an automated response any time outbound.

The second weakness is the lack of an IDS rule that detects or responds to lateral
movement via SMB. The IDS alert logs show that at 10:45 on June 24, lateral movement was
detected originating from 10.1.1.45 and directed at internal host 10.1.2.10 via SMB. This
alert was generated nearly 40 minutes after the affected machine was supposedly isolated
from the network at 10:07, suggesting that the isolation was incomplete. More critically, it
reveals that no automated response was triggered. The IDS identified the lateral
movement, but there is no evidence in the artifacts that a containment action, escalation,
or block rule was automatically applied in response. The current incident response
procedure describes containment as manually isolating a machine by disabling its network
port. 

This gap is exploitable in precisely the way that occurred in this incident. Once a RAT
or other malware gains a foothold on a single endpoint, lateral movement is the next
objective. The attacker seeks to expand access to other systems, elevated privileges, or
reach sensitive data. SMB is particularly common as a lateral movement vector because it
is a native Windows protocol that is often permitted across networks, under the
assumption that it is legitimate file-sharing traffic. In FinSecure’s environment, the absence
of both internal firewall controls on SMB traffic and automated IDS responses to lateral
movement alerts meant the attacker had a clear path to the HR subnet. Exposing the
attacker to all sensitive data.

The proposed rule to address this weakness is, first, to create an IDS rule
specifically to detect SMB connection attempts originating from workstation-class subnets
and directed at a host in another subnet. The rule is configured to automatically trigger a
network isolation response. Such as an ACL update to the relevant switch port or firewall
zone, rather than just logging it. This transforms the IDS into an active response instead of a
passive tool. Second, a complementary firewall rule should be implemented that explicitly
denies SMB traffic on ports 445 and 139 between user workstation VLANs and any subnet
that does not have a documented and approved file-sharing dependency. This rule should
be given high priority, so it is evaluated before the broad permit rules currently in place. This
directly supports all three pillars of the CIA triad. Confidentiality is protected by preventing
unauthorized access to systems beyond the initial compromise point. Integrity is
maintained by limiting the attacker's ability to modify or corrupt data on secondary hosts.
Availability is preserved by containing the incident to a smaller blast radius so that critical
systems remain operational during and after a security event.

Reference List
Cichonski, P., Millar, T., Grance, T., & Scarfone, K. (2012). Computer security incident
handling guide (NIST Special Publication 800-61 Rev. 2). National Institute of Standards and
Technology. https://doi.org/10.6028/NIST.SP.800-61r2

CISA. (2023). Cybersecurity best practices for network defenders. Cybersecurity and
Infrastructure Security Agency. https://www.cisa.gov/resourcestools/resources/cybersecurity-best-practices

National Security Agency. (2021). Embracing a zero trust security model. NSA
Cybersecurity Information Sheet. https://media.defense.gov/2021/Feb/25/2002588479/-
1/-1/0/CSI_EMBRACING_ZT_SECURITY_MODEL_UOO115131-21.PDF

NIST. (2020). Security and privacy controls for information systems and organizations (SP
800-53 Rev. 5). National Institute of Standards and Technology.
https://doi.org/10.6028/NIST.SP.800-53r5

Scarfone, K., & Hoffman, P. (2009). Guidelines on firewalls and firewall policy (NIST Special
Publication 800-41 Rev. 1). National Institute of Standards and Technology.
https://doi.org/10.6028/NIST.SP.800-41r1

Scarfone, K., & Mell, P. (2007). Guide to intrusion detection and prevention systems (IDPS)
(NIST Special Publication 800-94). National Institute of Standards and Technology.
https://doi.org/10.6028/NIST.SP.800-94


