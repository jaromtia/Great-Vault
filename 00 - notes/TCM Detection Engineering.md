#projects/tcm 
#resources/detection-engineering
Threat Hunting - Finding threats using logs across one or multiple devices.

Detection Engineering - Creating custom ruling and being able to test such rules. Testing relies on being able to recreate the vulnerability or IOC and detecting it

SOC analyst - Actioning based off of custom alerting across or for vendors

Threat Intelligence - collecting information on IOCs done by well known hacktivists organizations

# NIST Incident Response Lifecycle

1. Preparation
    1. Create custom rules for alerting
    2. Have the right amount of tooling for the job
    3. Prep infrastructure
2. Detection and analysis
    1. Alert and find the source of the IOC or threat actor
3. Containment
    1. Make sure the threat can not spread to other environments
4. Eradication and Recovery
    1. Destroy the threat and any trace of footholds. Recover what was lost. Mitigate what information was stolen.
5. Post analysis
    1. How can we improve? Take findings into preparation

# Detection engineering workflow (Repeatable process)

- Information Gathering
    - Initial Requirements
        - Any links to other tickets? Does the request have the necessary information?
    - New Log Source
        - Where is it coming from?
    - Prioritization
        - Which log sources should be focused on first
- Unit Testing
    - Review Log Source → Perform Test → Review Data
    - Why is it important?
        - Determines if the alert actual works rather than using a hypothetical
        - Limits gaps
        - Repeatable
        - Tool validation
- Alert Development
    - Start off at a high level then narrow down
    - Initial Query → Refinement → Enrichment → Finalize
    - source = bad url → source=email link=bad url → From the bad domain are there any hits within the network → source=email with bad url link within specific network
- Documentation - needs to be standardized and forced
    - Needs to be standardized
        - Sigma
        - Vendor
            - Splunk
            - Elastic
        - Customer
    - Tools - need to store these documents
        - github
        - python
        - [uncoder.io](http://uncoder.io)
        - socprime
- Peer Review - Final alert is validated and can be performed by detection engineers and incident response teams
    - Detection Engineer peer review → IR handover → Documentation uploaded → alert enabled → ticket closed

# What Makes A Good Detection?

False Positive / Volume of ticket ratio

- Are there a large number of alerts but mostly false positives? Bad detection

Testability

- Is the detection tested and repeatable?
- unit testing?

Specificity

- is the alert catching unrelated activity?

Response Feedback

- Is information missing from the alert?

Timeliness

- will the alert trigger when it happens or have delayed response?

Compensating Controls

- is detection alerting on an identified gap in security tooling?