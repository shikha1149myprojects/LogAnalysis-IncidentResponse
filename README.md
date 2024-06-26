# LogAnalysis-IncidentResponse


## Scenario

It is early in the afternoon on Wednesday October 18th, 2023.  You’re a busy member of your organization’s cybersecurity team who is fighting the urge to take a nap after you finish your lunch.  You decide to talk a short walk around your organization’s building to get the blood flowing again.  On your walk around the building you run into your CIO who asks you if the organization is vulnerable to the latest Cisco IOS XE vulnerability.  You say you aren’t sure but you’ll investigate and get back to them.

Returning to your desk you review some mailing lists and websites you monitor for security issues you see there are 2 CVEs that people are discussing which are being used together as part of an attack campaign by an unknown attacker - CVE-2023-20198 and CVE-2023-20273.  Doing some Googling you find a security advisory from Cisco and a blog post from Talos, Cisco’s threat intelligence team about the issue.
On your organization’s internal chat system you message your counterparts on the networking team for their assistance to help determine if your routers are vulnerable but get out of office messages for all of them.  Then you remember that the entire networking team is at an offsite team building event today and are unreachable.  You’ll have to figure out if any of your routers are vulnerable, or even worse, already compromised yourself.

Because your organization believes strongly in separation of duties and the principle of least privilege you don’t have an account on your routers so you can’t simply log into them to check the current version number.  But you do have access to your attack surface management tool and after review you do spot a router that had a public facing IP address assigned to one of the router interfaces and it was listening on port 443 (HTTPS) indicating that the web UI for the router is operational and exposed to the world.  

Time to review the logs from the routers (a copy of which is provided) along with the Cisco Security Advisory, Cisco Talos blog post, and the Talos Indicators of Compromise (IOCs) to determine if the router is vulnerable to CVE-2023-20198 and CVE-2023-20273 and if it has been compromised.


### Scenario Notes

Scenario Notes:

-The internal IP address of the router is 10.10.9.4

-The IP range for your network management tools is 10.99.1.0/24.

-NetMRI is a configuration tool used to manage network devices.  Seeing frequent logins from NetMRI to review and update configurations of networking devices is common and should be treated as legitimate when it comes from an IP address in a network management IP range.

-netmri is the name of the account utilized at your organization for NetMRI.

-Steve Williams (User ID: steve) and Blair Hamilton (User ID: blairh) are your organization’s network engineers. Logins for their accounts from your network management IP range should be treated as legitimate.


### Tools Used

-Splunk: SIEM tool that manages and provides insight into your organization’s cybersecurity. It collects, analyzes, and reports on log data generated throughout your organization’s digital environment

## Questions to Answer

-Was the router compromised?

-If it was compromised, when was it compromised?

-If it was compromised, can you determine if the attacker did anything post-compromise?

-Since you aren't actually performing them in this scenario what containment, eradication, and recovery steps would you recommend be taken?

-What are the lessons learned?
