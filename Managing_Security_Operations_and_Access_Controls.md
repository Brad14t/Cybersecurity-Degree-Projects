# Introduction

Organizations face ongoing cybersecurity threats that require well-defined procedures for detection, response, and recovery. Security professionals must be able to evaluate incident response plans for effectiveness and resilience and ensure network configurations are secure and optimized to prevent and mitigate attacks. In this task, you will act as a cybersecurity analyst to review an organization’s incident response process and network security posture and propose improvements to strengthen overall protection.

# Assignment

A.  Apply an access control model to the provided user role matrix and access control policies in the attached "Security Operations Artifact" by doing the following:

1.  Choose an access control model to apply to the provided user role matrix, and explain how the principles of your chosen model apply to the organization's access control structure.

2.  Identify four misalignments in the provided user role matrix based on your chosen access control model, and explain how each misalignment conflicts with your model’s principles.

3.  Recommend three changes to resolve the misalignments identified in part A2. Justify each recommendation based on applicable industry standards, frameworks, or best practices (e.g., NIST SP 800-53, ISO/IEC 27001, CIS Controls, principles from the SSCP Common Body of Knowledge).

4.  Revise the provided user role matrix to reflect your chosen access control type and to incorporate the changes recommended in part A3.



B.  Evaluate the organization's access control policies and related operational practices by doing the following:

1.  Identify three policy gaps or inconsistencies in the organization’s access control policies that could affect access management or operational security.

2.  Recommend one policy change or update for each gap identified in part B1 to strengthen policy alignment with security best practices.



C.  Using the attached "Security Operations Artifact," evaluate the organization's broader operational processes and practices (e.g., change management, security awareness, asset handling, physical security operations). Include the following elements in your evaluation:

•   an identification of three weaknesses in operational practices

•   an explanation of how each identified weakness affects the confidentiality, integrity, or availability (CIA) of organizational information

•   a recommendation of one improvement to address each identified weakness

 

D.  Analyze the system logs provided in the attached "Security Operations Artifact" to identify potential security threats by doing the following:

1.  Identify three threats within the system logs, and classify each threat by type (e.g., insider, malware, brute force, misconfiguration).

2.  Propose one mitigation strategy for each identified threat, and justify each strategy by referencing a recognized operational risk analysis model (e.g., NIST RMF, OCTAVE, ISO 27005) or accepted security best practices (e.g., CIS Controls, least privilege).

 

E.  Acknowledge sources, using in-text citations and references, for content that is quoted, paraphrased, or summarized.

 

F.  Demonstrate professional communication in the content and presentation of your submission.

# My Essay

he access control model I am applying to FinSecure Corp’s user role matrix is RoleBased Access Control (RBAC). RBAC is a model in which system access permissions are
assigned to roles rather than individual users. And users acquire permissions by being
assigned to one or more roles. This model is formally defined in NIST SP 800-53 AC-2
(Account Management) and AC-3 (Access Enforcement). RBAC aligns directly with
FinSecure Corp’s organizational structure because the company already groups employees
by department and job function, such as finance, HR, IT, security operations, marketing,
etc. Under a properly implemented RBAC model, each job function maps to a defined role,
for example, Finance Analyst, HR Coordinator, or SecOps Analyst. Each role carries a
specific pre-approved set of system permissions. No user received access beyond what
their assigned role requires. This enforces the principle of least privilege.
Three core principles of RBAC that apply to FinSecure Corp are the principles of
least privilege, separation of duties, and the need-to-know principle. Least privilege
ensures no user holds excessive rights. Separation of duties prevents a single user from
controlling an entire sensitive process end-to-end. Need to know restricts access to
sensitive data to only those whose role legitimately requires it, reducing the attack surface
if a single user is compromised.

The first misalignment is with an HR Assistant, P. Ellis. P. Ellis is listed with an end
date of 2025-05-20 and a role history not of “Terminated (2025-05-20)”, yet the account
status column shows “Active”. Furthermore, the system logs confirm a successful login by
P.Ellis on 2025-06-29 at 15:32:44Z from IP 198.51.100.42, a date much later than the
recorded termination date. This is a direct violation of RBAC principle that access should
be tied to the active role membership. A terminated employee holds no role within the
organization. Therefore, no permission should be assigned. According to NIST SP 800-52
“requires that accounts are disabled when no longer needed” (NIST, 2024). And FinSecure
Corp’s own Access Control Policy section 8 states that “access should be revoked within
seven days of the end date.” Leaving this account active creates a significant insider threat
and unauthorized access risk.

The second misalignment is with a Junior System Admin, J. Lopez. With this role, the
user would reasonably work with scoped administrative tasks under supervision. However
the system logs show a privilege escalation at 10:25:11Z on 2025-06-29. “PRIV_ESCALTION
user=j.lopez granted_privilege=”Domain Admin” target_account=j.lopez
method=manual_change” J. Lopez manually elevated his own account to Domain Admin,
granting himself unrestricted control over the entire Active Directory environment. This
directly violates RBAC’s least privilege principle and separation of duties. His role of junior
admin doesn’t require domain-level privileges, and a self-service privilege escalation is a
critical failure. NIST SP 800-53 requires that privileged account assignments be explicitly
authorized.

The third misalignment is with a Customer Support Rep, J. Hall. They are listed as
customer support rep, with access to the CRM and email server. Both are appropriate for
the support role. However, J. Hall is also listed as having access to the payroll system,
which has no relationship with customer support functions. Under RBAC, a support rep
role should be scoped to customer-facing systems only. Granting this excessive access
violates the least privilege and need-to-know principles. The Access Control Policy section
states that RBAC roles should align with business functions and defined permission sets,
and that any expectations must be documented with business justification. None of which
are present in the matrix.

The fourth misalignment is with an External Auditor, D. Nguyen. They are listed as an
external contract auditor with a contract end date of 2025-06-15. The account still shows
“Active” as of the review date. The system logs confirm a successful login on 2025-06-30 at
10:02:10Z from IP 212.85.112.101 with the log field “after_contract_end=2025-06-15”.
Meaning the authentication system itself flagged this as a post expiration access event.
Under RBAC, contractor roles are time-bound. Once the engagement ends, the associated
role assignment must be revoked. FinSecure Corp’s Access Control Policy, section 2,
states that contractor access may be provisioned for the duration of their engagement, and
section 8 requires that access be revoked within 7 days of the end date. This account was
active for longer than the required period.

Misalignments 1 and 4 both involve accounts that remain active after their
respective end dates. FinSecure Corp’s Access Control section 8 already requires
revocation within 7 days, but the policy is inconsistent. The recommended change is to
implement an automated, identity lifecycle-integrated offboarding workflow that ties HR or
contract management system end date records to the identity provider. So that accounts
are automatically disabled on or before the expiration date without manual intervention. An
automated solution eliminates human delays and ensures policy compliance, regardless
of whether an HR manager or an IT member remembers to submit a manual deactivation
ticket. This recommendation aligns with NIST SP 800-53 AC-2, which requires organizations
to disable accounts when they are no longer needed.

Misalignment 2 involves J. Lopez manually granting himself Domain Admin
privileges. A self-service process that bypasses approval. The recommended change is to
enforce a formal privilege access management (PAM) workflow in which privilege
assignments require multi-party approval, at a minimum, the user’s direct manager and an
IT security team member. Also, reconfigure the Active Directory environment so that no
user can grant elevated privileges to their own account without the approval workflow
being satisfied. This recommendation is grounded in NIST SP 800-53 AC-6, Domain Admin,
and similar highly privileged roles must be scoped, audited, and never self-assigned.
Misalignment 3 involves J. Hall holding payroll system access that is entirely outside
the defined scope of a customer support rep role. This type of out-of-scope access is likely
the result of ad-hoc access grants that were never reviewed against the formal RBAC role
definition. The recommended change is to conduct a comprehensive access review that
compares each user’s current system exception and documents the results in the service
request portal, as required by the Access Control Policy, section 3. NIST SP 800-53 AC-2
and AC-6 require periodic access reviews to ensure least privilege is maintained. CIS
control 6.3 requires MFA for externally exposed applications. Control 6.7 also emphasizes
that access rights must be verified against business requirements on a recurring basis.
Going forward, FinSecure Corp should define each RBAC role in a formal role catalog,
associate specific permissions with each role, and require written business justification for
any access granted outside the catalog, consistent with Access Control Policy section 10.
The table below reflects the RBAC model applied across all 24 accounts. Each entry
has been assigned a formal RBAC role name. All changes are documented in the Changed
Noted column. Red “Account Status” cells mean the account must be disabled
immediately. Amber “Change Notes” cells were made to align RBAC role definitions and
the least privilege principle.

View Full Data Table (PDF)
Gap 1 is that access reviews lack a defined frequency and accountability. Section 3
of the Access Control Policy states, “department managers are responsible for reviewing
user access as needed,” and “review results must be documented in the service request
portal.” The phrase “as needed” is not a defined schedule. It is entirely subjective and
leaves timing and thoroughness of reviews up to the individual. The user matrix itself is
evidence of this gap. J. Hall has payroll access that has no connection to a support role. L.
Cheng had CRM access outside her finance role, neither of which would exist under a
functioning periodic review process. There is no defined review interval, no escalation path
if a manager fails to conduct a review, and no audit trail required beyond a vague portal
documentation note.

Gap 2 is the offboarding process that relies entirely on manual manager action with
no verification step. Section 8 states that “managers must submit account deactivation
requests when staff leave the organization.” And that access should be revoked within
seven days of the end date. However, there is no verification step, no automated
enforcement, and no consequence defined if a manager fails to submit the request. The
operational practices overview reinforces this gap. Assets are expected to be returned to
the manager with no formal verification, and there is no documented process for wiping or
reimaging returned devices. The result is exactly what is shown in the logs: P. Ellis
terminated on May 20 but successfully logged in on June 29. And D. Nguyen, whose
contract expired June 15, logged in on June 30. The policy sets a seven-day standard but
provides no mechanism to enforce it.

Gap 3 is the logging and monitoring policy that allows unrestricted access to system
logs. Section 9 states that “access to logs shall be unrestricted to aid in troubleshooting.”
This is a direct security risk. System logs contain sensitive information, including user login
activity, failed authentication attempts, administrative actions, and potentially indicators of
compromise. Allowing any user unrestricted access to logs means a malicious insider or
compromised account could review logs to understand detection capabilities, identify
what activity is being monitored, and cover their tracks more effectively.

Recommendation for gap 1 is to mandate quarterly access reviews with a defined
owner and escalation path. The policy should be updated to require access reviews on a
defined schedule. At a minimum, quarterly for privilege accounts and semiannually for all
standard accounts. Alongside that, this policy needs a named reviewer, a hard deadline,
and an escalation path to the security department. This aligns with NIST SP 800-53 AC-2,
which requires accounts to be reviewed regularly, and ISO/IEC 27001 annex A.9.2.5, which
mandates periodic review of user access rights at a defined interval. The revised policy
should define “access review” concretely by comparing each user's actual permissions
with their current role.

Recommendation for gap 2 is to implement an automated, HR-integrated account
deactivation workflow with mandatory verification. Section 8 should be updated to require
that account deactivation be triggered automatically when an employee's end date is
entered in the HR system, rather than relying on a manager to manually submit a request.
The policy should be changed to disable the account on the actual end date, rather than a
7-day window. After the automated action is complete, a receipt confirming the action was
complete should be generated and logged as proof of deactivation. For contractors and
vendors, the identity system should enforce expiration dates at provisioning time so
accounts cannot remain active past the contract end date. This recommendation applies
to NIST SP 800-53 AC-2, CIS Control 6.2, and ISO/IEC 27001 annex A.9.2.6. The seven-day
window should be treated as an absolute maximum for edge cases, not an operational
standard.

Recommendation for gap 3 is to restrict log access to security and IT personnel only,
with exceptions requiring approval. Section 9 should be revised to state that access to
system logs is restricted by default to security and IT personnel only. And any other use
case should be approved via management with a documentation trial. This aligns with NIST
SP 800-53 AU-9, which explicitly requires that audit logs and tools be protected from
unauthorized access, modification, or deletion. The current policy's justification of
“unrestricted access aids troubleshooting” can be saved by granting read-only access to
relevant IT staff on a need-to-know basis.

The first weakness of the broader operational process is that change management
lacks formal documentation and review requirements. The operational practices overview
states that firewall and critical security device changes are made by IT administration with
no formal requirement to document change requests. In ticketing systems, emergency
changes can be made without managerial approval, and there is no post-change review
process. The logs provided evidence supporting this, T. Miller on 2025-06-30 at 09:49:33Z
modified firewall rule fw-internal-allow with the field ticket_id=None, meaning a change to
a critical security boundary device was made with zero documentation trail.
This weakness primarily affects integrity and availability. Without documented
change requests, there is no baseline to compare when something breaks. If a rule change
opens an unintended path to the network or blocks legitimate traffic, there is no postchange review to catch it. Availability is at risk because undocumented emergency
changes made without approval could inadvertently take down critical systems with no
rollback plan. Integrity is at risk because an insider could modify firewall rules to allow data
exfiltration, with no paper trail linking the change to the specific actor or business
justification.

My recommendation would be to introduce a formal change management policy
requiring that all changes to firewalls and critical security devices be submitted through a
ticketing system prior to implementation. Including a documented business justification
and rollback plan. Also needing manager approval, except in actual emergencies, and
undergo a post-change review within 24 hours of implementation.

The second weakness of the broader operational process is that security awareness
training is superficial and fails to develop practical skills. The operational practices
overview states that employees receive a short security awareness email annually, no
phishing simulations or practical training exercises are conducted, and new employees
receive only a five-minute verbal briefing from their manager during onboarding. This is a
very ineffective approach to security awareness. A single annual email does not build
behavioral habits, and a five-minute verbal briefing from a manager who is not a security
professional. Cannot adequately convey the threat landscape employees face. The system
logs support this, J. Hall on 2025-06-30 at 08:15:56Z queried the known malicious domain
xyzmalware.com, suggesting the user either clicked a phishing link or was otherwise
socially engineered. Phishing simulation training is designed to prevent.

This weakness affects all three pillars of the CIA triad. Confidentiality is at risk
because a phishing susceptible employee can be manipulated into surrendering
credentials or sensitive information. Integrity is at risk due to malware delivered via
phishing or social engineering, as evidenced by the GhostX RAT alert on K. Patel’s device.
Can modify, encrypt, or corrupt organizational data. Availability is at risk because
ransomware and destructive malware, commonly delivered through phishing, can render
systems and data inaccessible.

My recommendation is to replace the annual email with a structured, ongoing
security awareness program that includes role-based training modules, delivered at least
quarterly. Also, simulated phishing is conducted at regular intervals with immediate
remedial training for employees who fail. And a formal onboarding security training session
delivered by the security team.

The third weakness of the broader operational process is that physical security
controls are inconsistently enforced and unmonitored. The operational practices overview
identifies three physical security failures: keycards are not always deactivated immediately
after loss or theft, server room access logs are not regularly reviewed, and visitors are
required to sign in but are not always escorted by staff. Each of these is a standalone
weakness, but together they create a physical security posture that is very ineffective.
This weakness most directly affects confidentiality and integrity. Integrity is
compromised because physical access to servers or network equipment enables an
attacker to introduce hardware implants, tamper with configurations, or directly access
systems to bypass software-based access controls. Availability is at risk because
unauthorized physical access to a server room could result in hardware sabotage, power
disruptions, or equipment destruction, taking affected systems offline.

My recommendation is to enforce three immediate procedural changes: first,
establish a mandatory keycard deactivation SLA for lost or stolen cards to be reported and
deactivated within one hour. With the process designated to facilities staff. Second,
implement a weekly automated review of server room access logs. Third, enforce a strict
visitor escort policy with no exceptions.

The first threat identified in the system logs is a brute-force attack, followed by a
successful login from an unknown geographic location. The logs show the following
sequence on 2025-06-29:
08:47:12Z – Login Failure user=j.hall src_ip=185.63.145.20 reason=Invalid password
(attempt 5 of 5)
08:50:02Z – Login_Success user=j.hall src_ip=185.63.145.20 geo=Unknown (outside
normal range)
08:15:56Z (next day) – Suspicious_Query user=j.hall query_domain=xyz-malware.com
match_type=known_malicious
This is a textbook account compromise sequence. The attacker exhausted five password
attempts and then succeeded on a sixth from the same external IP address, which is
geolocated as unknown and outside J. Hall’s normal range. The fact that the login
succeeded after five failures from a foreign IP strongly suggests the account was
compromised, either through credential stuffing with a previously leaked password or
brute-force. The subsequent malicious domain query the following morning further
supports the conclusion that the account was actively being used by a threat actor.
The mitigation strategy should include implementing account lockout policies that
permanently lock an account after a defined number of failed attempts (the industry
standard is 5) and require an administrator to unlock the account or verify identity before
access is restored. Implementing MFA for all user accounts so that credential compromise
alone is insufficient to gain access. geolocation based conditional access controls should
flag or block login attempts from unknown regions pending secondary verification. This
mitigation adheres to NIST SP 800-53 AC-7, which requires that organizations enforce a
limit on consecutive failed login attempts and lock accounts when that limit is exceeded,
and CIS Control 6.3, which mandates MFA for all accounts, particularly those with access
to sensitive systems.

The second threat analyzed in the system logs is malware detection, specifically
GhostX Remote Access Trojan. The logs show the following on 2025-06-29:
14:54:08Z – Malware_Alert host=10.1.1.45 user=l.patel malware_family=”GhostX RAT”
severity=HIGH signature_id=GX-3492
11:47:59Z – Alert_Cleared alert_id=1472 cleared_by=k.patel reason=”False positive”
A remote access trojan is a category of malware that enables an attacker to gain covert,
persistent remote control over an infected host. GhostX RAT is flagged as high severity,
meaning the endpoint detection system has high confidence in the signature match. What
makes this threat particularly concerning is the earlier log showing that K. Patel, the
security analyst, whose machine was infected. Cleared the SIEM alert earlier that same
day, classifying it as a false positive.

The mitigation strategy should be to isolate host 10.1.1.45 from the network,
preserve a forensic image of the system before remediation, and initiate an incident
response process that treats the alert-clearing event as potentially related to the
compromise. Long-term, implement a separation-of-duties control requiring that SIEM
alerts be reviewed and cleared by a second analyst. Deploy endpoint detection and
response (EDR) tooling with automated containment capabilities so that high-severity
malware detection triggers automatic host isolation. This mitigation strategy aligns with
NIST SP 800-53 IR-4, SI-3, and AU-6, all of which require that malware detections be
escalated, investigated, and responded to through a formal incident-handling process.
The third threat analyzed in the system logs is reconnaissance activity from an
external port scan against the internal subnet. The logs show the following on 2025-06-30:
07:40:21Z – Port_Scan_Detected src_ip=102.54.18.99 target_subnet=10.1.20.0/24
protocol=TCP port_range=1-1024
A port scan across the full well-known port range (1-1024) of an internal subnet is a
deliberate reconnaissance activity, not incidental traffic. The source IP is an external
address probing the internal subnet, which means either the network perimeter has a
misconfiguration that allows external TCP traffic, or the scan is originating from a host that
already has some level of network presence. The timing of this scan is also notable. The
scan occurred the morning after J. Hall’s account was queried against a known malicious
domain, suggesting this could be part of a coordinated intrusion sequence.


The mitigation strategy should include immediately blocking the source IP
102.54.18.99 at the perimeter firewall and investigating how external TCP traffic reached
the internal subnet. This subnet should not be reachable from the internet without passing
through a DMZ or firewall allow rule. Long-term, implement network segmentation so that
internal subnets are separated by function, and no single external entry point can reach all
internal subnets. Deploy an intrusion detection and prevention system with automated
blocking rules that trigger port-scanning patterns rather than logging them. This mitigation
aligns with the OCTAVE risk analysis framework, which emphasizes identifying critical
assets and the paths to them. 

[C845 Assignment 1 (1).pdf](https://github.com/user-attachments/files/26760533/C845.Assignment.1.1.pdf)

[Revised_User_Role_Matrix_Clean (1).pdf](https://github.com/user-attachments/files/26760602/Revised_User_Role_Matrix_Clean.1.pdf)

