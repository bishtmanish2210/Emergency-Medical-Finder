System Design Overview

This solution is designed as emergency medical information
infrastructure rather than a traditional consumer application.
The primary goal of the system is to reduce decision-making
delay during medical emergencies, where time, connectivity,
and data reliability cannot be guaranteed.

The system assumes worst-case conditions by default:
Network connectivity may be unstable or unavailable
Hospitals may not update availability data in real time
User traffic may spike suddenly during emergencies
Perfect accuracy is not always achievable

Based on these assumptions, the architecture prioritizes
availability, fault tolerance, and fast response over
absolute real-time correctness.

The system follows a read-heavy, stateless service design
where user queries are served quickly from cached and
replicated data sources. Hospital and doctor availability
updates are handled asynchronously to avoid blocking
user requests.

Instead of binary availability (open/closed), the system
treats hospital status as a time-sensitive signal whose
reliability decays over time. This allows the platform
to continue providing ranked and useful suggestions
even when data freshness is uncertain.

Overall, the architecture is intentionally designed to
degrade gracefully rather than fail completely, ensuring
that users receive the best possible information under
emergency conditions.
