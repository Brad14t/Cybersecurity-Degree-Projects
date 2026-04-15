# Introduction

Cybersecurity professionals often encounter ethical dilemmas when safeguarding sensitive data and ensuring compliance with legal and regulatory standards. These professionals must balance the need for privacy, transparency, and legal compliance with the practical realities of securing information systems. Failing to maintain this balance can lead to legal consequences, loss of reputation, and harm to the individuals whose data is compromised. To navigate these challenges effectively, organizations need strong internal training initiatives, such as the Security Awareness Training and Education (SATE) program, that equip employees with the knowledge to handle ethical and security issues.

In this task, you will continue using the same organization and its information security policy documentation selected in Task 1. You will build on the deficiencies identified in Task 1 and develop a Security Awareness Training and Education (SATE) program tailored to that organization.

# Assignment

A.  Identify the organization (FinEd or TeleMedica) from the information security policy documentation referenced in the Supporting Documents section and describe two potential ethical challenges the organization could face due to non-compliance with legal regulations and cybersecurity standards.

 

B.  Predict three consequences the organization identified in part A might face if a data breach occurred during the period of non-compliance.

 

Note: The consequences could include a data breach's legal and non-legal ramifications.

 

C.  Propose two ways the organization identified in part A could improve its culture of compliance, excluding the use of a Security Awareness Training and Education (SATE) program.

 

D.  Explain two ways a SATE program fosters a culture of compliance for the organization identified in part A.

1.  Describe two ways leadership can support SATE programs for the organization identified in part A.

 

E.  Develop a SATE program outline designed explicitly for the organization identified in part A. The outline must include the following elements:

1.  Describe two ways the SATE program will address the areas in which the organization identified in part A previously failed to meet known security standards or legal regulations.

2.  Describe two proactive security measures the program will address for the organization identified in part A.

3.  Write one program objective for each security measure from part E2.

4.  Describe the key topics that should be covered for each security measure from part E2.

5.  Describe the actions employees should take for each security measure from part E2.

6.  Describe the training format for each security measure from part E2.

7.  Describe the evaluation metrics that will be used to measure the success of the program for each security measure from part E2.

 

F.  Describe two mechanisms for soliciting and using feedback for continuous improvement of the SATE program.

 

G.  Acknowledge sources, using in-text citations and references, for content that is quoted, paraphrased, or summarized.

 

H.  Demonstrate professional communication in the content and presentation of your submission.

# My Essay

As identified in task 1, TeleMedica’s data protection and privacy policy specifies that
data in transit is encrypted using SSL v2.0. A protocol formally prohibited by the Internet
Engineering Task Force through RFC 6176. This was due to well-known, documented
cryptographic vulnerabilities. This significant deficiency creates an ethical challenge
rooted in the concept of informed trust. When patients use TeleMedica’s systems, they
share some of the most sensitive personal information possible. Like mental health
records, chronic disease data, and cross-border health information. Patients have a
reasonable expectation that the organization is taking every appropriate measure to
protect them. TeleMedica’s own policy states its commitment to processing data “lawfully,
transparently, and securely.” (TeleMedica, 2024). Continuing to transmit patient data over a
deprecated, vulnerable protocol while simultaneously representing the company as secure
and trustworthy. This creates a direct ethical contradiction when a company promises one
thing but delivers another.

The second ethical challenge stems from TeleMedica’s password policy. As
identified in task 1, this required the password to be changed every 90 days, with no other
complexity requirements, and no MFA. This deficiency creates an ethical challenge
centering around equity of protection. Specifically, whether TeleMedica provides all
patients with an equal and adequate standard of data security, regardless of which
employee or system they use to access their records. The healthcare sector is one of the
most targeted industries for credential-based cyberattacks. Weak authentication protocols
are at the heart of the primary enabler of unauthorized access to patient records. Without
MFA, this poses risks to patients in the event of a breach. The ethical concern is that
patients whose data is at risk have no visibility into or control over authentication practices.
They are entirely dependent on TeleMedica to take responsibility for their private
information. This challenge also intersects directly with NIST Special Publication 800-63B,
which identifies MFA as a necessary safeguard for systems handling sensitive personal
data. Without MFA, knowingly withholding MFA would be a breach of the duty of care.


The first consequences of a data breach would be legal and financial penalties
across multiple jurisdictions. Given that TeleMedica falls under multiple jurisdictions. A
data breach occurring during the period of non-compliance identified in task 1 would
expose the organization to simultaneous legal and financial penalties from multiple
regulatory bodies. At the federal level, a breach involving ePHI (electronic personal health
information) occurred during the period of knowingly using SSL v2.0 encryption. Violates
HIPAA’s Security Rule under 45 CFR, 164.312 (a) (1) and 164.312 (e) (1) (HHS,1996). The
U.S. Department of Health and Human Services Office for Civil Rights has the authority to
impose civil monetary penalties ranging from $100 to $50,000 per violation. With an annual
maximum of $1.9 million per violation category. And if the case proves to be willful neglect,
these penalties will be mandatory and not discretionary. And since the company uses SSL
v2.0, which has been prohibited since 2011, it would make it very difficult for the
organization to argue that the vulnerability was unknown. At the international level, a
breach affecting data shared with MediCom GmbH or involving EU residents would trigger
a GDPR enforcement. Under GDPR article 83, organizations can face fines of up to €20
million or 4% of global annual turnover, whichever is greater. Article 32 specifically requires
that appropriate technical measures be implemented to protect personal data, and the use
of deprecated encryption would be a direct and easily documentable failure of this
requirement.

Beyond the immediate legal and financial consequences, a data breach would carry
severe, potentially lasting reputational consequences that could fundamentally undermine
the organization’s ability to operate as a trusted telehealth provider. Unlike many other
industries, healthcare operates within a uniquely intimate trust relationship between
provider and patient. The reputational damage from a breach in this context is simply not a
public relations problem; it directly affects patients’ willingness to seek care, disclose
symptoms honestly, and engage with telehealth services at all. The reputational harm will
extend beyond the patient base. The organization’s collaborative relationships depend on
mutual confidence in each party’s security posture. The breach will damage all existing
relationships and sister companies, undermining the ability to conduct cross-border
services. Any company publicly identifying with the breach will have to discuss the
potential harm of being associated. Reputational damage could far outweigh the impact of
a regulatory fine.

The third consequence TeleMedica could face is significant operational disruption
and irreversible data loss, compounded by the backup and recovery deficiencies. With the
recovery point being identified in task 1 being up to a week old, potential critical patient
data could be unrecoverable. If the breach involved ransomware and the systems were
compromised, the organization would have to choose between paying a ransom to recover
the data or accepting the loss of up to weeks’ worth of patient records. Neither option is
acceptable for a healthcare provider. NIST Special Publication 800-34 establishes that
“recovery point objectives for systems handling sensitive or critical data should be
determined by the maximum tolerable data loss the organization can sustain for an active
telehealth platform. This threshold is measured in hours, not days.” (NIST, 2020). The
operational disruption would extend further still, with quarterly recovery testing as the only
validation of backup integrity. TeleMedica has limited assurance that its London failover
center will perform reliably in the event of an actual breach. This risk can be mitigated via
more frequent testing. 

The first way TeleMedica could meaningfully improve its compliance culture is by
establishing a formal compliance governance structure. This will assign clear, dedicated
accountability for information security and regulatory compliance at the leadership level. A
culture of compliance isn’t merely sending out policy documentation. It requires visible
and sustainable organizational commitment from leadership to all employees that security
and compliance are priorities rather than obligations. First, this would start with appointing
a dedicated Chief Information Security Officer (CISO), or equivalent compliance role. They
would have to oversee TeleMedica’s compliance with HIPAA, GDPR, CCPA, and other
applicable regulations. They would maintain a compliance roadmap that tracks known
deficiencies. Ensuring gaps like SSL encryption and insufficient authentication controls.
The CISO would report to executive leadership and present compliance status updates.
You could further strengthen this position by including a cross-functional compliance
committee. They would represent IT, security, legal, clinical operations, and HR. This all
helps with NIST compliance, since they require clearly defined accountability and
communication within an organization.

The second proposal to improve TeleMedica’s compliance culture is to implement a
continuous compliance monitoring and incentive program. This reinforces compliant
behavior at the employee level. Since a compliant environment requires everyone to buy in.
This program needs to incentivize employees and leadership to hit a certain level.
Continual compliance monitoring would involve deploying automated tools that provide
real-time visibility into compliance-relevant behaviors. Such as flagging unauthorized
software installations, monitoring policy violations in data handling, and tracking whether
employees are adhering to access control procedures. This directly addresses a weakness
in TeleMedica’s current approach, which relies on manual weekly reviews of network logs
by the Security Operations Center. Automated continuous monitoring reduces this gap by
enabling faster identification of compliance failures. The incentive dimension of this
proposal is equally important. A culture of consequences for doing things wrong and none
for doing things correctly is a flawed model. “Research consistently demonstrates that
punitive-only compliance cultures — where employees hear about security exclusively in
the context of what they must not do or face consequences for — are less effective at
producing sustained compliant behavior than cultures that also recognize and reward
positive compliance contributions” (ISO, 2022). This incentive program is particularly good,
given the ethical challenges. Creating an environment where employees feel empowered
and rewarded for raising security concerns will lead to earlier escalation and prevent
potential breaches.

One of the most significant ways a SATE program fosters a culture of compliance at
TeleMedica is by closing the gap between written security policies and employees' day-today behaviors. As evidenced throughout task 1, TeleMedica has established a range of
security policies. However, the existence of these policies alone does not guarantee that
employees understand them or apply them to their work. A SATA program translates
complex regulatory and technical requirements into role-specific guidance that employees
can use daily.

The second way a SATE program fosters a culture of compliance at TeleMedica is by
cultivating a shared sense of responsibility and ethical accountability among employees.
Shifting the mindset from viewing security as the exclusive domain of the IT department. To
understand that it is a collective obligation that every member of the organization shares.
As identified, TeleMedica’s non-compliance deficiencies create ethical challenges that
extend beyond regulatory consequences. They represent a potential breach of duty of care
owed to the patients who trust this organization with their sensitive data. A SATA program
that explicitly connects security practices to patient welfare and organizational ethics
helps employees understand not just what they are required to do, but why it matters.
When an employee fully understands that failing to follow proper data-handling procedures
or to report suspicious activity could directly compromise a patient's health records.
Compliance will become a moral commitment rather than a checkbox.

The first and most impactful way TeleMedica’s leadership can support the SATE
program is through visible, active participation, combined with consistent executive
endorsement, signaling to all employees that security awareness is a priority. If
TeleMedica’s executives, department heads, and clinical leaders are seen completing SATE
modules, attending awareness sessions, and discussing security topics in communication,
it sends a message that compliance is shared across the organization.

The second way TeleMedica’s leadership can support the SATE program is by
committing the organizational resources needed to develop, deliver, and improve it. Treat
the program as a strategic investment rather than a one-time compliance activity.
Leadership should focus on continual improvement. A static program that is developed
once will quickly become outdated. Leadership should establish a formal review cycle. At a
minimum, yearly. Leadership should support measuring the SATE program using defined
metrics, like phishing simulation results, policy acknowledgment rates, and incident
reporting frequency. Use the metrics to demonstrate program effectiveness.

The SATE program directly addresses TeleMedica’s reliance on this outdated
encryption standard and its insufficient use of authentication controls. By ensuring
employees across all roles understand both the technical reality of these vulnerabilities
and their personal responsibility in either perpetuating or helping remediate them. The
technical aspect is upgrading to TLS 1.3 and implementing MFA. The SATE program ensures
that employees understand why these controls exist and how to use them correctly once
implemented. Specifically, this program will include dedicated training modules on secure
data transmission practices and proper authentication. Teaching employees to identify
warning signs of insecure connections and understanding the importance of MFA in
protecting patient data.

The SATE program also addresses TeleMedica’s inadequate backup frequency and
recovery testing cadence by ensuring that employees understand their role in data
continuity. Not as a passive user of systems that are backed up automatically, but as active
participants in identifying risks to data integrity. Most employees may be unaware of the
organization's recovery point objectives, location of failover systems, or procedures they
are expected to follow. This program will include training on TeleMedica’s disaster recovery
procedures, including departmental continuity plans, communication protocols with
MediCom HmbH during cross-border incidents, and the steps employees must take to
preserve data integrity and report anomalies. This ensures TeleMedica’s leadership
increases backup frequency and recovery testing cadence as recommended in task 1.

The first proactive security measure the SATE program will address is the
organization's wide adoption and correct use of MFA across all systems that access patient
data. This program will proactively prepare TeleMedica’s workforce to understand and
embrace the correct use of MFA as a foundational security control. This, in parallel with the
lack of a password policy, will greatly increase the security posture.

The second proactive security measure the SATE program will address is phishing
and social engineering awareness. Credential-based attacks are consistently identified as
the leading cause of healthcare data breaches. Given the global reach of this organization,
the risk of a successful phishing attack is elevated. 

The objective for MFA awareness and implementation is to ensure that 100% of
TeleMedica’s employees with access to patient information systems can correctly explain
the purpose of MFA, successfully complete the MFA enrollment process, and demonstrate
proper MFA use.

The objective of the phishing and social engineering awareness module is for
employees to identify three common indicators of phishing attempts and social
engineering tactics. Demonstrate the correct procedure for reporting suspicious
communications to the SOC. And show a measurable reduction in phishing simulation
click rates of at least 70% compared to the pretraining baseline.

The MFA training module will cover the following key topics. First, an explanation of
what MFA is and why a password alone is insufficient to protect sensitive systems.
Including a plain-language explanation of credential-based attacks, such as brute-force,
credential stuffing, and password spraying. Second, an overview of TeleMedica’s specific
MFA implementation, including which systems require MFA, the available authentication
methods (e.g., authenticator apps and hardware tokens), and how to complete enrollment.
Third, the correct procedure for handling MFA-related issues, such as lost devices, locked
accounts, or suspicious unauthorized authentication attempts.

The phishing awareness module will cover the following key topics. First, an
overview of phishing and social engineering as attack vectors. Including email phishing,
spear phishing, vishing, and pretexting. Second, practical identification of phishing
indicators, including suspicious sender addresses, urgent threat language, unexpected
links, or attachments. Third, TeleMedica’s specific reporting procedure for suspicious
communications, like how to submit a report to the SOC analyst as required by the incident
response policy.

Employees are expected to take the following actions regarding the MFA security
measure. Upon notification from the IT security team, all employees must complete the
MFA enrollment process for their assigned systems. Employees must use MFA every time
they access patient information. If an employee loses access to their MFA device or makes
any unexpected authentication attempts, they must immediately contact the IT security
team and report the incident to the SOC. Employees are also obliged to complete the MFA
SATE module and refresher training within the established deadline. 

Employees are expected to take the following actions in connection with the
phishing awareness security measure. Upon receiving any communication, email, phone
call, or message. Employees must refrain from clicking links, downloading attachments, or
providing any credentials or sensitive information when exhibiting phishing indicators
covered in the training module. They must report these suspicious communications.
Employees will be required to participate in periodic phishing simulation exercises
conducted by the SOC. They must also complete all phishing training with the SATE
module.

The MFA training module will be delivered in a blended format combining
asynchronous e-learning with live, role-specific technical walkthroughs. The asynchronous
component will be hosted on TeleMedica’s learning management system. Consistent with
the mandatory training delivery mechanism already established in the acceptable use
policy. Each interactive e-learning module will be approximately 30 minutes with video
explanations, scenario-based knowledge checks, and a final comprehensive assessment
that the employee must pass. The live component will consist of small-group technical
walkthrough sessions led by IT security staff, tailored to each employee's group's systems. 

The phishing awareness module will be delivered through a continuous, simulationbased training format. Combining an initial foundational e-learning module with ongoing
simulated phishing exercises. The foundational knowledge will be delivered via
TeleMedica’s learning management system. Each module will be 45 minutes in length and
will include video-based instructions, real-world healthcare phishing case studies, and an
interactive scenario exercise in which employees practice identifying and reporting
phishing communications. Following this module, the SOC will conduct monthly phishing
simulation exercises in which realistic but controlled phishing emails are sent to
employees without prior notice. Their click rates and report rates are tracked and analyzed.
Those who fail will have to complete additional training modules. 

The success of the MFA training module will be measured by the enrollment
completion rate and the training assessment pass rate. With a goal of achieving a 100%
completion rate for all employees. Next, measure the comprehensive assessment on their
first attempt, aiming for 90% or higher. In the background, the IT security team will review
system logs to assess the frequency of attempts to bypass MFA controls. Lastly, the help
desk ticket volume will be monitored to indicate any gaps in training or enrollment support. 

The success of the phishing awareness module will first be measured with the
phishing simulation click rate. The percentage of employees who click on links in the
simulated exercise. With a target reduction of no less than 70% from baseline within six
months of module release. Second suspicious communication reporting rate: the
percentage of simulated phishing emails correctly identified and reported to the SOC, with
a target of 60% higher within six months. Third will be repeat click rate, tracking whether an
employee who's previously clicked a simulated phishing attempt repeats this behavior.
With a target of below 10%.


TeleMedica will administer brief post-training surveys immediately following
completion of each SATE module through the organization. These surveys will capture four
categories of feedback relevant to the employee’s role, clarity of the material,
completeness of topic coverage, and satisfaction with the training format. Results will be
reviewed quarterly by the CISO and the compliance committee. In addition, TeleMedica will
establish an open-ended feedback channel, where all employees can submit suggestions
for new topics, concerns, and any observations.

The second mechanism uses the evaluation metrics established as a continuous
feedback signal. Monthly, the SOC will compile and analyze the program's key performance
indicators. Where metrics fall below established targets, this triggers a structured review of
the relevant training module to determine whether content, format, or delivery requires
adjustments. Findings will be shared with the CISO and compliance committee for
quarterly review.

Reference List
European Parliament & Council of the European Union. (2016). Regulation (EU) 2016/679
(General Data Protection Regulation). https://eur-lex.europa.eu/legalcontent/EN/TXT/?uri=CELEX%3A32016R0679

Federal Trade Commission. (1914). Federal Trade Commission Act, 15 U.S.C. § 45.
https://www.ftc.gov/legal-library/browse/statutes/federal-trade-commission-act

International Organization for Standardization. (2022). ISO/IEC 27001:2022 — Information
security, cybersecurity and privacy protection. https://www.iso.org/standard/27001

National Institute of Standards and Technology. (2003). SP 800-50: Building an information
technology security awareness and training program. U.S. Department of Commerce.
https://csrc.nist.gov/publications/detail/sp/800-50/final

National Institute of Standards and Technology. (2010). SP 800-34 Rev. 1: Contingency
planning guide for federal information systems. U.S. Department of Commerce.
https://csrc.nist.gov/publications/detail/sp/800-34/rev-1/final

National Institute of Standards and Technology. (2018). Framework for improving critical
infrastructure cybersecurity (NIST Cybersecurity Framework). U.S. Department of
Commerce. https://www.nist.gov/cyberframework
