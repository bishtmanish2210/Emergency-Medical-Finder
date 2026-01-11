The system is designed to scale horizontally.

Key strategies:

Stateless request handling

Read-heavy architecture using cache replication

Asynchronous processing of updates

No single point of failure in the read path

During sudden spikes (disasters, accidents), cached responses allow the system to continue serving users without overload.
