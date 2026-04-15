# Introduction

In this task, you will act as an IT security manager working for an organization. As part of your role, you have been asked to evaluate the organization's current information security compliance, risk, and governance, and then write a brief report to present to senior leadership.

# Assignment

A.  Write a brief report for senior leadership on the organization's current information security compliance, risk, and governance by doing the following:

1.  Identify the organization in the case study. Include two laws or regulations relevant to the organization.

a.  Discuss how each law or regulation applies to the organization identified in part A1.

b.  Recommend two policies or procedures the organization could implement to address each law or regulation identified in part A1.

i.  Discuss how each policy or procedure will increase compliance.

2.  Describe two potential threat events that could occur as a result of exploiting an associated vulnerability in the case study. Include in the description for both potential threat events:

•  An overall likelihood rating (Very Low/Low/Moderate/High/Very High) with justification based on the likelihood the threat event will occur and the likelihood that the threat event will result in adverse impacts,

•  An impact rating (Very Low/Low/Moderate/High/Very High) with explanation of potential consequences to business operations due to the occurrence of each threat event,

•  A level of risk rating (Very Low/Low/Moderate/High/Very High) based on the likelihood and impact assessment ratings,

•  A discussion of a risk management approach for the organization in the case study that is based on the levels of each risk rating.



Note: Refer to the link provided in the A2 rubric for guidance on how to complete your Risk Analysis.



3.  Recommend two modifications to the organization's existing information security policies or procedures to improve information security governance.

a.  Explain how each recommendation will increase information assurance levels within the organization.

 

B.  Acknowledge sources, using in-text citations and references, for content that is quoted, paraphrased, or summarized.

 

C.  Demonstrate professional communication in the content and presentation of your submission.

# My Essay

[D832 Assignment 1 (1).pdf](https://github.com/user-attachments/files/26763118/D832.Assignment.1.1.pdf)

A1. The organization in the case study is Sandhaven University (SU), a private, nonprofit
higher education institution headquartered in Los Angeles, California. SU enrolls about
25,000 students annually and manages sensitive data including student educational
records, financial transactions, personal health information (PHI), and research data. Two
laws directly applicable to SU are the Family Educational Rights and Privacy Act (FERPA)
and the Health Insurance Portability and Accountability Act (HIPAA).

A1a. FERPA governs the privacy of student educational records and applies to any
institution receiving federal funding, which SU does through NSF grants and federal
financial aid programs. SU stores and disseminates student PII, through the Registrar’s
Office, third party student information systems, and cloud based platforms. FERPA
requires that student records are protected from unauthorized disclosure and that
students have the right to access and request amendments to their records. SU’s
Registrar’s office currently faces a 90 day backlog in responding to records requests an has
acknowledged difficulty validating proper consent before releasing records, representing a
direct compliance gap.

HIPAA applies because SU operates on-campus health clinics and manages PHI related to
student health services. Under HIPAA’s Security Rule, covered entities must implement
administrative, physical, and technical safeguards to protect electronic PHI. The
ransomware incident in the College of Healthcare building, which halted critical operations
and compromised systems across an entire network segment, demonstrates that SU’s
health related systems are insufficiently protected and that existing safeguards do not
meet HIPAA standards.

A1b. For FERPA, the first recommendation is a records access and consent verification
procedure. SU should implement a standardized, documented process requiring written or
authenticated electronic consent before a students records are released. With mandatory
logging of every request and its outcome. This directly addresses the registrar’s inability to
validate requests under current conditions. This increases compliance, since FERPA
requires that institutions obtain valid consent prior to disclosing personally identifiable
information. A formal procedure with audit trails ensures that each release is traceable,
reviewable, and defensible during federal audits. Reducing the likelihood of unauthorized
disclosure that would constitute FERPA violations.

The second recommendation is a third party data sharing agreement policy. SU should
require that all vendors handling student records, sign data sharing agreements that
specify FERPA compliant data handling, access controls, and breach notification
obligations. Such as the third party SIS and the record management solution. It increases
compliance since FERPA permits disclosure to third party vendors only under the “school
official” expectation, which requires that the institution maintain direct control over the
data and that vendors use it for only authorized purposes. Formalizing these agreements
ensures SU retains oversight and establishes enforceable standards, directly satisfying this
regulatory requirement.

For HIPPA the first recommendation is an incident response and breach notification policy
for PHI. SU should create a policy specifically governing the identification, containment,
and reporting of incidents involving ePHI. Including mandatory notification timelines
aligned with HIPPA’s Breach Notification Rule “Obligate the business associate to report to
the covered entity any security incident of which it becomes aware, including breaches of
unsecured PHI as required by the Breach Notification Rule.” (HHS, 2013). It increases
compliance because a HIPAA specific incident response policy ensures that breaches are
identified and reported within regulatory timeframes, preventing the penalties associated
with unreported breaches. During the ransomeware incident, SU made no law enforcement
notifications and filed no insurance claims despite paying $100,000 ransom, suggesting an
absence of formal breach response procedure. 

The second recommendation is technical safeguards and access control policy aligned
with HIPAA Security Rule. This policy should mandate encrypted transmission of ePHI,
role-based access controls for health systems, and network segmentation separating
healthcare systems from general university networks. This will increase compliance with
HIPAA Security Rule (45 CFR 164.312) “The Security Rule sets forth the administrative,
physical, and technical safeguards that covered entities and business associates
(collectively, “regulated entities”) must put in place to secure individuals’ electronic
protected health information.” (HHS, 2013) Enacting this policy moves SU toward meeting
those explicit technical requirements.

A2. Threat event one is a phishing-initiated ransomware deployment via unfiltered external
email. SU’s email environment lacks inbound filtering capable of detecting spoofed sender
addresses originating outside the SU domain. The ransomware incident in the College of
Healthcare confirmed a clinical instructor opened a malicious attachment from an external
sender that resembled a student email address, and no security alerts were triggered.

Likelihood of initiation is rated High (80-95). Phishing campaigns targeting universities are
well documented, and SU presents an attractive target given its large user base of 25,000
students and 2,500 staff with varying levels of security awareness. The existing security
training program covers topics largely irrelevant to SU’s threat environment. Such as
threats to elected officials and tax data regulations. Meaning employees are not
adequately prepared to recognize phishing attempts. The adversary is highly likely to
attempt this type of attack given the confirmed success in the prior incident

Likelihood of adverse impact is rated High (80-95). The prior incident demonstrated that
once a malicious attachment is opened, TrickBot, Cobalt Strike, and Maze ransomware
were able to propagate across an entire network segment with no automated detection
stopping the spread. If initiated again, it is highly likely to result in adverse impact. With
high initiation and high adverse impact yields an overall likelihood of High.

The impact rating is High given the ransomware incident halted all critical operations
across the College of Healthcare’s network segment, rendered 46 hosts inoperable, and
require a $100,000 ransom payment. A reoccurance would severely degrade SU’s ability to
perform primary functions, resulting in major financial loss, and create significant harm to
individuals whose PHI may be exposed. This aligns with a High impact rating, constituting a
severe or catastrophic adverse effect on organizational operations on assets. (NIST SP 800-
30, page 85). With the intersection of a High overall likelihood and High impact yields a
level of risk of High.

Given the high risk rating, SU should pursue a risk mitigation strategy rather than risk
acceptance. Immediate actions should include deploying email filtering with domain
authentication protocols (SPF, DKIM, DMARC) to block spoofed external senders, and
implementing endpoint detection and response (EDR), to identify malicious behavior
before lateral movement. Network segmentation should be enforced across all facilities,
not just reactive isolation after an incident. Security awareness training should be replaced
with a program tailored specifically to SU’s threat profile, with phishing simulation
exercises conducted regularly. 

The second threat event was data exfiltration via unpatched file transfer software. SU
deployed MOVEit Transfer version 12.0 without patch management plan, update
documentation, or vulnerability identification procedures. CVE-2023-34362 was actively
exploited for approximately 90 days before discovery, during which time research data and
student financial records were exfiltrated. The root cause explicitly identifies the absence
of continuous network monitoring and limited firewall configurations as enabling factors.
The likelihood of initiation is rated Very High (96-100). SU has already experienced this
exact threat event. The continued absence of a formal patch management program and
vulnerability management process means that similar unpatched software vulnerabilities
are likely present across the environment today.

Likelihood of adverse impact is rated Very High (96-100). The prior incident ran undetected
for 90 days due to absence of continuous monitoring. Without corrective action, a repeated
exploitation would almost certainly result in adverse impacts. And the environment that
allowed this has not been fundamentally changed based on the case study’s current
controls. The intersection of Very High initiation and Very High adverse impact yields an
overall likelihood of Very High.

The impact rating is High, the exfiltrated data including student financial records and
faculty research data, which carries FERPA implications, potential NSF grant compliance
consequences, and reputational damage. The involvement of the FBI field office and the
need for third party remediation contractor indicate that this event causes severe
degradation. A severe adverse effect on organizational operations, assets, and individuals.
(NIST SP 800-30) With the combination of Very High overall likelihood and High impact
yields a level of risk of Very High. 

A Very High risk rating requires immediate and decisive action. Risk acceptance is not
appropriate at this level. SU must implement a formal patch and vulnerability management
program that establishes a defined cycle for identifying, assessing, and remediating
software vulnerabilities across all systems, with critical patches applied within a defined
SLA. Continuous network monitoring must be established, with a SIEM or equivalent tool.
Capable of detecting anomalous outbound data transfers. Edge firewall configurations
should be hardened wit egress filtering rules to limit the volume and destination of
outbound data. Given that SU has only four IT managing security functions as secondary
duties, leadership should also accelerate the goal already identified in SU’s security
objective, “establishing a dedicated cybersecurity team”, as the current staffing model is
structurally incapable of managing Very High residual risk. Until those controls are in place,
SU should consider engaging a managed security service provider (MSSP) as an interim
measure.

A3. The first recommendation is to overhaul the password policy to meet modern
standards. SU’s current password policy has been in place since 2012 and requires only a
six-character minimum with annual rotation and no complexity or history requirements.
This falls significantly below current industry standards and creates exploitable weakness
across all systems, including those storing FERPA protected record and PHI. The
modification should update the policy to require a minimum of 12-16 characters, enforce
complexity requirements (uppercase, lowercase, numbers, special characters), prohibit
password reuse, and mandate MFA for all admin accounts and any system containing
sensitive data. Password changes should be triggered by suspected compromises rather
than on a fixed schedule, consistent with current NIST guidelines.

A3a. Information assurance depends on ensuring that only authorized users can access
sensitive systems and data. A weak password policy is a direct attack surface, short,
noncomplex passwords are vulnerable to brute force and credential stuffing attacks, both
of which are common against higher education Institutions. Adding MFA introduces a
second layer of verification so that even a compromised password alone is insufficient for
access. This directly strengthens the confidentiality and integrity pillars of information
assurance by substantially reducing the probability of unauthorized system access.

The second recommendation is to replace the generic security training with a role-based
SU specific program. The current security training is a standardized state employee course
covering topics that are unrelated. This modification should replace this with a role-based
program on phishing recognition and safe handling of PHI. IT staff should receive training
on vulnerability management, incident response, and patch management procedures.
Administrative staff handling financial or student records should be trained on FERPA
obligations and social engineering threats. Training frequency should increase to twice
annually, and completion should be tracked and enforced with documented
consequences for non-compliance. Phishing simulation exercises should be incorporated
as a measurable component.

The ransomware incident in the College of Healthcare originated from a clinical instructor
who opened a malicious attachment. A failure that role specific phishing awareness
training directly addresses. Human error remains the leading cause of security incidents,
and a training program that does not address the actual threats employees face provides
little protection. By aligning training content to each roles specific risk exposure, SU
reduces the likelihood of successful social engineering across the organization. This
strengthens the availability and integrity of SU’s systems by reducing the probability of
incidents that result in operational disruption, data loss, or unauthorized access. 

Reference list
U.S. Department of Education. (2023). FERPA general guidance for students.
https://studentprivacy.ed.gov/ferpa

U.S. Department of Health and Human Services. (2013). Summary of the HIPAA Security
Rule. https://www.hhs.gov/hipaa/for-professionals/security/laws-regulations/index.html
D832 Case Study 4: Sandhaven University. (n.d.). WGU course materials.

National Institute of Standards and Technology. (2012). Guide for conducting risk
assessments (NIST SP 800-30 Rev. 1). https://csrc.nist.gov/publications/detail/sp/800-
30/rev-1/final

National Institute of Standards and Technology. (2020). Digital identity guidelines:
Authentication and lifecycle management (NIST SP 800-63B). https://pages.nist.gov/800-
63-3/sp800-63b.html
