# Introduction

In this task, you will act as an IT security manager working for an organization. The organization is planning the development of an incident response plan. You have been asked to provide recommendations for key sections of the plan.

# Assignment

A.  Develop recommendations for the organization's incident response plan by doing the following:

1.  Identify the organization in the case study and discuss two types of cybersecurity incidents or events that should be addressed in the incident response plan.

a.  Recommend a tool or technique to detect each incident or event from part A1.

b.  Recommend an action to contain each incident or event from part A1.

i.  Discuss how each action aligns with the security goals for the organization identified in part A1.

2.  Recommend two roles and their responsibilities to improve the organization's incident response capabilities.

a.  Discuss how each role will help maintain business continuity.

3.  Recommend a metric that could be used to measure the effectiveness of the incident response plan.

4.  Discuss how the incident response plan should be communicated to stakeholders.

 

B.  Acknowledge sources, using in-text citations and references, for content that is quoted, paraphrased, or summarized.

 

C.  Demonstrate professional communication in the content and presentation of your submission.

# My Essay

[Develops Security Incident Response Plans (1).pdf](https://github.com/user-attachments/files/26763230/Develops.Security.Incident.Response.Plans.1.pdf)

A1. Sandhaven University (SU) is a private, nonprofit higher education institution in Los
Angeles, California. Enrolling about 25,000 students annually and employing 2,500 faculty
and staff. SU manages a wide range of sensitive data including student PII, financial
transaction records, protected health information (PHI), and confidential research data.
Given SU’s demonstrated history, two cybersecurity incidents that must be addressed in
their incident response plan are ransomware attacks and software vulnerability
exploitation leading to data exfiltration. Ransomware was directly experienced when
TrickBot malware and Maze ransomware infected 100% of the active hosts on the nursing
buildings network segment, ultimately costing SU $100,000 in cryptocurrency. The attack
originated from a phishing email, highlighting the risk posed by SU’s large and diverse user
population. Data exfiltration via software vulnerability exploitation was demonstrated
through MOVEit Transfer incident, where CVE-2023-34362 allowed a threat actor to access
research data and student financial records undetected for about 90 days, stemming
directly from outdated software and a lack of continuous network monitoring.

A1a. To detect ransomware, SU should deploy an endpoint detection and response (EDR)
solution. EDR tools provide continuous, real-time monitoring of endpoint behavior,
suspicious activity alerting, unusual process execution, and lateral movement. During the
College of Healthcare incident, initial alerts came only via telephone calls from confused
users, meaning there was no automated detection in place. An EDR platform would have
fagged the anomalous behavior far earlier in the attack chain. 

To detect software vulnerability exploitation and data exfiltration like the MOVEit incident,
SU should implement a security information and event management (SIEM) system paired
with network traffic analysis. A SIEM aggregates and correlates logs from across the
environment, and can alert on indicators of compromise such as unusual outbound data
transfers or exploitation attempts against known CVEs. The 90 day undetected exfiltration
window in the MOVEit incident was directly attributable to the absence of continuous
network monitoring, which a properly tuned SIEM would address.

A1b. To contain a ransomware attack, SU should implement immediate automated
network segmentation, isolating the affected segment from the rest of the network the
moment ransomware indicators are detected. During the healthcare incident, a network
administrator manually isolated the affected segment after receiving dozens of phone calls
over four hours. Automated segmentation triggered by EDR alerts would dramatically
reduce the spread window, potentially containing the attack to a fraction of the hosts
affected.
To contain a software vulnerability exploitation event like MOVEit, SU should establish a
formal vulnerability and patch management process that includes emergency patch
procedures. Upon receiving notification of a critical CVE, this process would mandate
immediate system isolation. In the MOVEit incident, a generic service ticket was created
with no urgency or governance. An emergency patch protocol would have close the
vulnerability rapidly rather than allowing exploitation to continue for 90 days.

A1i. Automated network segmentation directly aligns with SU’s security goals of
maintaining business continuity through tested and validated procedures and ensuring at
least 99% uptime of student facing systems. By containing ransomware to the affected
segment quickly, critical systems across the rest of the university remain operational. It
also supports the goal of developing practices to prevent or minimize the impact of security
incidents, since a smaller blast radius means a faster and less costly recovery.

A formal patch management and emergency response process aligns with SU’s goals to
adopt unified solutions for security monitoring and patch management and to improve
cybersecurity governance across the organization. The MOVEit incident’s root cause was
explicitly tied to the absence of ay update planning or vulnerability remediation
documentation. Establishing a structured, enforceable patch process closes this
governance gap and directly reduces the risk of exploitation through known vulnerabilities.
Particularly important given SU’s reliance on third party platforms and cloud based
systems for sensitive data transmission and storage.

A2. Two roles SU should establish to strengthen its incident response capabilities are a
dedicated incident response manager and a cybersecurity analyst. The incident response
manager would serve as the central coordinator during a security event, responsible for
activating and overseeing the incident response plan. Making containment and escalation
decisions, communicating with leadership and external parties such as law enforcement
or vendors, and ensuring post incident reviews are conducted. Currently SU’s four network
and systems administrators are juggling security responsibilities as a secondary duty
alongside their primary IT functions. During the ransomware incident, the response was
reactive and disorganized. Notifications came by telephone, decisions were made without
cleat authority, and ultimately leadership paid a ransom without notifying law enforcement
or filling an insurance claim. A dedicated incident response manager eliminated this
ambiguity by providing a single accountable owner of the response process.

The cybersecurity analyst would be responsible for continuous monitoring of security
alerts, threat intelligence gathering, vulnerability tracking, and forensic analysis during and
after incidents. This role would operate the SIEM and EDR tools, triage alerts, and
escalating confirmed threats to incident response manager. The absence of this function
was the direct reason the MOVEit exploitation went undetected for 90 days, no one was
actively watching the network for indicators of compromise. 

A2a. The incident response manager supports business continuity by ensuring that when
an incident occurs, the response is structured, and decisive rather than improvised. SU’s
goal of maintaining at least 99% uptime for student facing systems cannot be achieved if
incident response depends on administrators who are already stretched across multiple
responsibilities. A dedicated manager reduces mean time to respond and mean time to
recover by having pre-established playbooks, vendor contracts, and escalation paths ready
to execute. During the healthcare ransomware event, the lack of this role led to hours of
delay and uncoordinated response that ultimately halted critical operations in the program
entirely. 

The cybersecurity analyst supports business continuity primarily through early threat
detection, which is the single most effective way to limit the operational impact of an
incident. Threats caught at the early stages of an attack chain require far less recovery
effort and cause far less disruption to academic and administrative operations. This
directly supports SU’s goal of developing practices to minimize the impact of security
incidents, and also advances the broader goal of establishing a dedicated cybersecurity
team to help mature the information security program.

A3. The most appropriate metric to adopt is mean time to detect (MTTD), which measures
the average time elapsed between the start of a security incident and the moment it is
identified by the organization. MTTD is calculated by tracking the difference between when
an incident began (determined through log analysis and forensic investigation), and when it
was formally detected. SU’s incident history makes MTTD the most revealing indicator of
plan effectiveness. The MOVEit exploitation ran undetected for approximately 90 days, and
the ransomware attack was only discovered through user phone calls after systems had
already failed across an entire network segment. Both cases demonstrate that SU’s core
vulnerability is not in its ability to respond once aware of an incident, but in the significant
delay before awareness is achieved at all. Tracking MTTD over time would give SU a
concrete, measurable signal of whether investments in tools like SIEM and EDR, and the
addition of the cybersecurity analyst role, are producing real improvements in detection
capability. As SU matures its incident response program, a declining MTTD trend would
validate that monitoring practices are working. Conversely a rising MTTD would signal that
tooling, staffing, or processes need reassessment. MTTD also pairs naturally with mean
time to respond (MTTR) as a secondary metric, since faster detection enables faster
containment. But MTTD should be the priority metric given SU’s most critical gaps.

A4. Stakeholder communications of the incident response plan must be tailored by
audience, since SU’s stakeholder groups (executive leadership, IT, staff, faculty, students,
and external partners), have different relationships to plan and need different levels of
detail.

Executive leadership and university administrators should receive a high level briefing that
focuses on their specific roles and decision making authorities during an incident,
escalating thresholds that require their involvement. Given that SU’s leadership made the
unilateral decision to pay a ransom without law enforcement notification or insurance
claim during the incident, it is critical that leadership understands in advance what the
established decision making chain look like and what obligations the university has during
a cyber event. 

IT staff, particularly the two newly recommended roles, require the most thorough
communication plan. This group should receive the full technical documentation including
playbooks, containment procedures, escalation contacts, and tool specific response
workflows. This should be a repeated exercise, with tabletop exercises and simulated
incident scenarios. SU’s existing security training is a generic state employee course that
needs major overhauling and continuous practice.

Faculty, staff, and students representing SU’s largest and most variable risk surface. The
healthcare ransomware attack originated from a clinical instructor opening a malicious
email attachment with no security triggered. This population does not need the technical
details of the plan, but they do need clear communication about their role in prevention.
Specifically, how to identify and report suspicious emails, links, and system behaviors. This
should be delivered through targeted awareness campaigns, not added into the existing
two-hour generic annual training session.

External stakeholders including third party vendors, the NSF given SU’s research grant
relationships, and legal bodies should be made aware of communication and notification
procedures that apply to them during an incident. SU’s handling of both prior incidents
shows a pattern of delayed or absent external notification, which carried legal and
regulatory risk given the sensitivity of the data SU manages. Establishing a pre-defined
notification template and timeline for external parties ensures SU meets its obligations
without having to improvise during an active incident.

Reference List

National Institute of Standards and Technology (NIST). (2012). Guide to computer security
log management (Special Publication 800-92). U.S. Department of Commerce.
https://doi.org/10.6028/NIST.SP.800-92

National Institute of Standards and Technology (NIST). (2018). Framework for improving
critical infrastructure cybersecurity (Version 1.1). U.S. Department of Commerce.
https://doi.org/10.6028/NIST.CSWP.04162018

Bhatt, S., Manadhata, P. K., & Zomlot, L. (2014). The operational role of security information
and event management systems. IEEE Security & Privacy, 12(5), 35–41.
https://doi.org/10.1109/MSP.2014.103


