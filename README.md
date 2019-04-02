# xapi-probe-deploy
Helm chart for deploying xAPI-Probe to Kubernetes


## Backup & Restore of Postgres database

##### Backup

From inside the postgres container run:

```bash
pg_dump --disable-trigger --data-only -U flask st3k101 > /mnt/st3k101_$(date --iso-8601).psql
```

##### Restore

From inside the postgres container run:

```bash
psql -f /mnt/st3k101_SOME-DATE.psql st3k101 flask
```
