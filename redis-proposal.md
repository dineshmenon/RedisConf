SAP Cloud Platform(SCP) is an open platform-as-a-service (PaaS) product that provides core platform and backing services, for building and extending cloud applications on multiple cloud infrastructure providers. SCP's fully managed Redis-as-a-service consists of 3 VMs - 1 Master and 2-Slaves. Data replication is done asynchronously between master and slaves with minimum one slave in sync with master throughout instance lifecycle.
Major features:
End-user configurable policies - Redis applications users can provide the values of policies like eviction and save according their use-case requirement during instance-creation.
Bi-weekly-Rolling-Updates-with-Near-Zero-Downtime - Redis sentinels backed by various custom scripts enables service to be available even during updates.
Persistence enabled cluster - RDB based persistence allows application to use redis as data store and not just cache.
 
Disaster-Recovery-using-Backup-and-Restore - Redis-as-a-Service instance provides snapshot based backup and restore mechanism. Snapshots are stored on cloud storage in AWS/Azure/GCP. Backups are scheduled and service remains available during backup. Recovery process involves creation of volume from snapshot and attaching that volume to the master node.
Centralized-Monitoring-System/Metrics-Collector- A monitoring agent runs as job in every Redis VM to report its service health metrics like service-availability|CPU|memory|disk-usage, and database information like stored keys, maxmemory utilization. The monitoring agent collects this information and reports it to centralized monitoring server, which stores in a time-series-database. A monitoring-web-application shows metrics via various charts so that devops can identify the instance health at any given time-date range
Centralized-Troubleshooting-System-for-all-Redis-as-a-Service-instances - All important system-logs and custom logs generated from a service-instance is pushed to a central system so that Ops can access them to trace any condition/debug any problems. Trouble shooter lets users debug any issue irrespective of service-instance availability.
Multi-channel-Alerting-System - Alerting-module raise alerts when some undesired state is reported, like "redis-server-not-available, maxmemory-size-threshold-crossed, backup-failed" among others.
 
 
