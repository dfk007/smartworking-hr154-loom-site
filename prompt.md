Create a set of 5 clean, modern educational infographic-style images for learning MongoDB Atlas for a DevOps / infrastructure interview. Each image should explain one high-priority topic clearly and visually.

Topics to cover:
1. MongoDB Atlas cluster architecture and scaling
2. MongoDB replication, elections, failover, and high availability
3. MongoDB backups, Point-in-Time Recovery, restore testing, and disaster recovery
4. MongoDB performance tuning, query analysis, and indexing
5. MongoDB security, networking, and access control

Style:
premium technical infographic design, dark theme, elegant UI-inspired visuals, subtle grid background, glowing database nodes, arrows for data flow, clear labels, dashboard-like panels, high contrast, minimal clutter, cinematic but educational, not flashy marketing, not cartoonish, no stock-photo style.

Goal:
help a learner understand the most important MongoDB Atlas concepts visually, with fewer ideas per image but stronger explanation.

Create these 5 images:

Image 1: MongoDB Atlas cluster architecture and scaling
Show:
- Atlas cluster tiers from lab to production
- Replica set vs sharded cluster
- Region and cloud provider choice
- Vertical scaling vs horizontal scaling
- Autoscaling boundaries
Visual layout:
- Left side shows a smaller cluster growing upward in size
- Right side compares replica set and sharded cluster
- Include cloud/region markers and scaling arrows
On-image labels:
- "M0/M10 for practice"
- "M30+ for production discussion"
- "Replica set vs sharded cluster"
- "Scale up first, shard when needed"

Image 2: MongoDB replication, elections, failover, and high availability
Show:
- One primary and multiple secondary nodes
- Oplog replication flow
- Heartbeats between nodes
- Primary failure triggering election
- New primary selected automatically
- Brief write interruption during election
Visual layout:
- Center cluster diagram with one green primary and blue secondaries
- Failure event shown as a red outage marker on the primary
- Election pulse and promotion of one secondary to new primary
On-image labels:
- "Primary"
- "Secondary"
- "Oplog"
- "Election"
- "Temporary write interruption"
- "Automatic failover"

Image 3: MongoDB backups, Point-in-Time Recovery, restore testing, and disaster recovery
Show:
- Snapshot backups on a timeline
- Point-in-Time Recovery between snapshots
- Restore to a new cluster
- Restore validation / testing workflow
- RPO and RTO concepts
Visual layout:
- Timeline view with snapshots and a PITR recovery point between them
- Arrow from source cluster to restored cluster
- Small checklist panel for restore validation
On-image labels:
- "Snapshots"
- "Point-in-Time Recovery"
- "Restore to new cluster"
- "RPO"
- "RTO"
- "Backup is not enough, test restore"

Image 4: MongoDB performance tuning, query analysis, and indexing
Show:
- Query without index causing collection scan
- Same query after adding compound index
- Explain plan comparison: COLLSCAN vs IXSCAN
- Example compound index on tenantId + status + createdAt
- Why filter and sort order matter
Visual layout:
- Left side red slow query path scanning many documents
- Right side green fast indexed path scanning fewer records
- Small explain-plan comparison panel
On-image labels:
- "explain(executionStats)"
- "COLLSCAN"
- "IXSCAN"
- "Compound index"
- "Match index order to filter + sort"

Image 5: MongoDB security, networking, and access control
Show:
- Restricted IP allowlist for lab access
- Private networking / VPC peering / PrivateLink for production
- Separate users for app, monitoring, and read-only access
- TLS, encryption at rest, KMS, audit logging
- Blocked unsafe public exposure like 0.0.0.0/0
Visual layout:
- Network boundary diagram with approved vs denied access
- Role-based user cards
- Security controls panel with lock/encryption/audit icons
On-image labels:
- "Least privilege"
- "IP allowlist"
- "Private networking"
- "TLS"
- "Encryption at rest"
- "Audit logs"
- "Avoid 0.0.0.0/0 in production"

Global requirements:
- Make the images educational first, beautiful second
- Use readable on-image text
- Keep diagrams simple and structured
- Use arrows, nodes, timelines, and dashboards to explain ideas
- Avoid stuffing too much into one image
- Make each image feel like part of one consistent visual series
- Use accurate technical relationships, not abstract decoration

Tone:
clear, calm, technical, accurate, confident, beginner-friendly but owner-level.

Output:
5 highly educational infographic-style images that help someone truly understand the most important MongoDB Atlas concepts for interview preparation.
