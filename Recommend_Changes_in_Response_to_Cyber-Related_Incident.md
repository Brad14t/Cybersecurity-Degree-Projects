# Introduction

In this task, you will act as an IT security manager working for an organization. As part of your role, you have been asked to identify and address deficiencies within the organization's security management program.  

# Assignment

A.  Identify the organization in the case study. Based on the post-incident reports in the case study, discuss two deficiencies in the organization's security management program.

1.  Recommend two changes to the security management program for each deficiency from part A.

a.  Explain how each recommended change could prevent similar incidents from occurring in the future.

 

B.  Acknowledge sources, using in-text citations and references, for content that is quoted, paraphrased, or summarized.

 

C.  Demonstrate professional communication in the content and presentation of your submission.

# My Essay

[Recommend Changes in Response to Cyber-Related Incident (1).pdf](https://github.com/user-attachments/files/26763294/Recommend.Changes.in.Response.to.Cyber-Related.Incident.1.pdf)

A. The organization in the case study is Sandhaven University (SU), a private, nonprofit
higher education institution located in Los Angeles, California. Enrolling about 25,000
students annually and managing sensitive data including student PII, financial records, and
protected health information.

The first deficiency is the inadequate patch and vulnerability management. The first post
incident report reveals that SU was running an outdated version of MOVEit Transfer (v12.0)
with no documented plan for software updates or vulnerability remediation. When a critical
vulnerability (CVE-2023-34362) was identified, the absence of any formal patch
management process meant a generic service request was created with no urgency or
governance behind it. This gap allowed threat actors to actively exploit research data and
student financial records for about 90 days before detection. Compounding the issue,
limited edge firewall configurations and a lack of continuous network monitoring allowed
data exfiltration to go undetected during that entire window.

The second deficiency is the insufficient email security controls and security awareness
training. The second post incident report shows that ransomware infection began when a
clinical instructor opened a phishing email that appeared to originate from a student but
was actually sent from outside the SU domain, triggering no security alerts. SU’s existing
security training is a generic two hour state employee course covering unrelated topics,
making it poorly suited to build threat recognition that could have prevented this incident.

A1. The first recommended changes to inadequate patch and vulnerability management is
implementing a formal patch management policy. SU should establish a documented
patch management policy that defines classification tiers for vulnerabilities (critical, high,
medium, low) and mandates corresponding remediation timelines, like for critical
vulnerabilities, patches should be applied within 72 hours of vender disclosure. 

A1a. This directly addresses the root cause of the first incident, by ensuring that a known
critical CVE triggers an immediate, structured response rather than a generic ticket. Had
such a policy existed, the MOVEit vulnerability would have been patched before or shortly
after exploitation began, dramatically reducing the 90 day exposure window. This policy will
be effective in the future, preventing an incident similar. 


A1. The second recommended change to inadequate patch and vulnerability management
is to deploy continuous monitoring with defined alerting thresholds. SU should adopt a
unified security monitoring solution (consistent with SU’s own security goals), which
provide real time visibility into network traffic and automated alerting for anomalous
outbound transfers.

A1a. The case study explicitly notes that external exfiltration was enabled by a lack of
continuous monitoring. With behavioral based detection in place, unusual data movement
to external destinations, like the MOVEit exploitation would have triggered alerts far earlier,
limiting the scope and duration of the breach.

A1. The first recommended change to insufficient email security controls and security
awareness is to deploy email security controls including external sender tagging and antispoofing protocols. SU should implement email attachment standards (SPF, DKIM, and
DMARC) alongside a policy that automatically appends a visible warning banner to all
messages originating outside the SU domain. Automated sandboxing of zipped
attachments from external senders would add a second layer of defense.

A1a. Because the phishing email resembled a student email address but originated
externally, a visible external sender tag would have given the instructor a clear warning.
Sandboxing a zipped attachment would have caught the malicious payload before it
reached the endpoint, preventing the initial access that led to the full ransomware
deployment.

A1. The second recommended change to insufficient email security controls and security
awareness is to replace generic training with role specific, scenario based phishing
awareness training. SU should replace its current state employee training with targeted,
scenario based training that uses realistic simulations, like student submission style
phishing emails. Pair that with regularly simulated phishing campaigns and remedial
training for those who fail.

A1a. The training bears no relevance to SU’s actual threat landscape. Repeated phishing
simulations build measurable resilience in staff and directly address the human factor that
served as the initial access point in incident 2. A user trained to recognize external sender
anomalies and suspicious attachments would have been far less likely to extract and open
malicious files in the future. 

Reference List

Western Governors University. (n.d.). D832 case study 4: Sandhaven University. Western
Governors University.


