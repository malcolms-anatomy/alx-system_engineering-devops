## Postmortem: Web Stack Outage

### Issue Summary
**Duration of the Outage:** June 15, 2024, 14:00 - 17:30 GMT

**Impact:** 
The web application experienced significant downtime, resulting in 80% of users being unable to access the service. Users faced 503 Service Unavailable errors or extremely slow response times when attempting to use the platform. This outage affected critical functionalities, including login, data retrieval, and form submissions.

**Root Cause:** 
The root cause was a misconfiguration in the load balancer settings, which led to an overload on a subset of servers, while others remained underutilized.

### Timeline
- **14:00 GMT:** Issue detected by automated monitoring systems, which triggered an alert for high response times and error rates.
- **14:05 GMT:** Engineers received alerts and started investigating the issue.
- **14:15 GMT:** Initial assumption was a database performance issue due to a recent update.
- **14:30 GMT:** Database team analyzed logs and metrics; no significant anomalies found.
- **15:00 GMT:** Application team suspected a code deployment issue and began rolling back the recent deployment.
- **15:30 GMT:** Rollback completed, but the issue persisted.
- **16:00 GMT:** Network team identified uneven traffic distribution across servers.
- **16:15 GMT:** Load balancer configuration reviewed and identified as the root cause.
- **16:30 GMT:** Correct load balancer configuration applied.
- **17:00 GMT:** System performance began to stabilize.
- **17:30 GMT:** Full service restoration confirmed; monitoring continued to ensure stability.

### Root Cause and Resolution
**Root Cause:**
The load balancer was incorrectly configured after a routine maintenance update. This misconfiguration resulted in a disproportionate amount of traffic being directed to a limited subset of servers, causing them to become overloaded and fail to handle incoming requests efficiently.

**Resolution:**
Upon identifying the misconfiguration, the network team adjusted the load balancer settings to ensure even distribution of traffic across all servers. They implemented the correct load-balancing algorithm and verified the settings. Once the correct configuration was applied, the traffic was evenly distributed, and the server load normalized, restoring the service to full functionality.

### Corrective and Preventative Measures
**Improvements and Fixes:**
1. **Review and Patch Load Balancer Configuration:** Ensure that load balancer settings are thoroughly reviewed and tested after every update.
2. **Enhanced Monitoring:** Implement more granular monitoring and alerting for load balancer metrics to detect similar issues early.
3. **Documentation and Training:** Update the maintenance procedures documentation to include specific steps for verifying load balancer configurations. Conduct training sessions for the network team.

**Tasks:**
- Patch the load balancer configuration immediately.
- Add monitoring for load balancer metrics (e.g., traffic distribution, server load).
- Review and update maintenance procedure documentation.
- Schedule and conduct training sessions for relevant teams.
- Perform regular audits of load balancer settings post-maintenance.

By addressing these corrective and preventative measures, we aim to prevent similar outages in the future and enhance the overall reliability of our web application.
