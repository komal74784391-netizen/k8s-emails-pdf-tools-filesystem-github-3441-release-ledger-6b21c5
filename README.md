# Workload Release Ledger

Authoritative ledger of every workload running on the Northwind Platform estate.

Each workload has exactly one entry at `catalog/<team>/<workload>.yaml`.
The owning team is also the Kubernetes namespace, and the workload name
is also the deployment name.

Entry fields:

- `team` - owning team / Kubernetes namespace
- `workload` - workload and deployment name
- `release` - ISO-8601 instant of the currently running release
- `channel` - `stable` or `canary`
- `owner` - responsible engineer
- `status` - `active` or `retired`

Entries are permanent: never delete an entry. A retirement changes only the
`status` field. The deployment itself is removed from the cluster.
