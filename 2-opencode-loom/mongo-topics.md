**MongoDB Atlas topics to know for this JD, in the right priority order**

This role is not asking for generic MongoDB awareness. It is asking for **production ownership of MongoDB Atlas** inside a DevOps / infrastructure role. Prioritize the topics below in this order.

---

### **1. Atlas cluster architecture and scaling**
- **Atlas cluster tiers and sizing:**
  - `M0` for practice.
  - `M10`, `M30+` and higher for production discussions.
- **Cluster types:**
  - Replica set for most standard production workloads.
  - Sharded cluster when horizontal scale, data volume, or throughput requires it.
- **Architecture choices you should explain:**
  - When to stay on a replica set vs when to shard.
  - Vertical scaling vs horizontal scaling.
  - Region placement, cloud provider choice, MongoDB version, storage growth, and autoscaling boundaries.
- **Terraform ownership:**
  - `mongodbatlas_advanced_cluster`
  - environment separation
  - remote state
  - reusable modules

---

### **2. Replication, elections, failover, and high availability**
- **Replica set internals:**
  - Primary, secondaries, oplog, heartbeat, quorum, elections.
- **Failover behavior:**
  - What happens to writes during primary election.
  - What clients see during failover.
  - Replication lag and stale reads.
- **Read and write behavior:**
  - Read preference.
  - Read concern.
  - Write concern.
- **Operational checks:**
  - `rs.status()`
  - `db.hello()`
  - Atlas test failover

---

### **3. Backups, PITR, restore testing, and disaster recovery**
- **Backup concepts:**
  - Snapshots.
  - Point-in-Time Recovery.
  - Oplog window.
- **Recovery language you must speak clearly:**
  - `RPO`
  - `RTO`
- **Restore behavior:**
  - Atlas restores to a new cluster.
  - Restore testing is as important as backup configuration.
  - Recovery plans need validation and cutover steps, not only backup retention.
- **Terraform / operations:**
  - backup schedule resources
  - hourly and daily retention
  - DR runbooks

---

### **4. Performance tuning, query analysis, and indexing**
- **Query investigation:**
  - `explain("executionStats")`
  - `COLLSCAN` vs `IXSCAN`
  - slow query review in Atlas Performance Advisor
- **Index types you should know well:**
  - single-field
  - compound
  - TTL
  - partial
- **Good production judgment:**
  - Index order should match filter and sort patterns.
  - Unindexed queries often become painful only after data grows.
  - More indexes improve some reads but add write cost and storage cost.
- **What else to understand:**
  - working set size
  - hot collections
  - connection behavior under load

---

### **5. Security, networking, and access control**
- **Database access:**
  - least-privilege users
  - scoped roles per database
  - separate users for runtime, migrations, analytics, and admin work
- **Atlas-level access:**
  - Atlas project roles
  - API keys for automation
  - secret handling
- **Network security:**
  - IP allowlist for labs
  - VPC peering / PrivateLink for production-grade connectivity
  - why `0.0.0.0/0` is not acceptable for production SaaS
- **Data protection:**
  - TLS in transit
  - encryption at rest
  - KMS integration
  - audit logs

---

### **6. Atlas observability, monitoring, and alerting**
- **Metrics to watch:**
  - CPU
  - memory pressure / cache behavior
  - disk utilization and growth
  - connections
  - query latency
  - replication lag
  - operation throughput
- **Atlas operational tooling:**
  - built-in metrics dashboards
  - Performance Advisor
  - alert policies
- **What owner-level thinking looks like:**
  - choose thresholds that reflect service risk
  - distinguish symptoms from root cause
  - know when to scale, re-index, tune queries, or reduce noisy workloads

---

### **7. Atlas operations with Terraform and automation**
- **Resources you should be comfortable with:**
  - advanced clusters
  - database users
  - IP access lists
  - backup schedules
  - private networking resources
- **Production Terraform expectations:**
  - modularization
  - remote state
  - multi-environment setup
  - safe plan / apply workflow
  - drift awareness
- **CI/CD fit:**
  - Atlas changes should go through reviewable infrastructure code, not only manual UI changes.

---

### **8. Capacity planning, cost, and scaling tradeoffs**
- **You should be able to explain:**
  - when to resize a cluster tier
  - when to enable or constrain autoscaling
  - when workload shape suggests sharding
  - cost vs performance tradeoffs for enterprise SaaS
- **Examples of owner-level questions:**
  - Is the issue compute, storage, indexing, replication lag, or bad query design?
  - Would a higher tier solve the problem, or only hide a modeling / indexing issue?

---

### **9. Incident response, runbooks, and production ownership**
- **You should know how to respond to:**
  - failover events
  - slow query incidents
  - connection spikes
  - backup or restore failures
  - access-control mistakes
- **Good operational maturity means:**
  - clear runbooks
  - post-incident RCA
  - long-term fixes, not only quick mitigation
  - communication that works in a remote async team

---

### **10. Nice-to-have Mongo topics for this role**
- **Useful, but lower priority than the sections above:**
  - multi-region design
  - zone sharding
  - live migration tooling
  - cross-cloud tradeoffs
- **Do not over-invest here before the core topics are solid:**
  - Atlas Search
  - Vector Search
  - certifications

---

### **Hands-on proof you should be able to show or describe**
- Create an Atlas cluster and explain the sizing choice.
- Provision the cluster, users, and access list with Terraform.
- Connect with `mongosh` and inspect replica-set state.
- Trigger a failover test and explain what changed.
- Create a backup policy and describe restore testing.
- Run an unindexed query, add an index, and compare `explain("executionStats")` output.
- Create a scoped read-only user and prove the write failure.
- Explain how you would secure Atlas in a production SaaS environment.

---

### **Best summary for this JD**
If you are short on time, focus on these five Atlas themes first:

1. Cluster architecture and scaling
2. Replication, failover, and high availability
3. Backups, restore testing, and disaster recovery
4. Performance tuning, query analysis, and indexing
5. Security, networking, and access control

Then add:

6. Observability and alerting
7. Terraform automation and multi-environment operations
8. Cost, capacity, and incident ownership
