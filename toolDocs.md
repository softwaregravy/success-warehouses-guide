## Title: Info
### Warnings

> 

### Syntax

> `tool info <target> <target-id>`

#### Parameters:

#### Return Value:

### Examples

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Report
### Warnings

> 

### Syntax

> `tool report (source | connector) <slug> <project_id> [--collection=<collection>, --source=<source>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Task Status
### Warnings

> 

### Syntax

> `tool task status [--source=<source> --connector=<connector> --workspace=<workspace>] [--running --failed --hanging --tail=<tail> --kill]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Source Runner - Run
### Warnings

> 

### Syntax

> `tool task force-run source --workspace=<workspace_slug> [--force] [--option=<options>...]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Warehouse Connector - Run
### Warnings

> 

### Syntax

> `tool task force-run connector (--workspace=<workspace_slug> | --project=<project_ids>...) [--force] [--option=<options>...]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Replay - Run
### Warnings

> 

### Syntax

> `tool task replay run (--workspace=<workspace_id> | --project=<project_id> ) (--full | --from=<from> --to=<to>) [--cluster-id=<cluster_id>] [--max-containers=<max_containers>] [--exclude-project=<exclude_project>...] [--max-error="<max_error>"] [--notify="<notify>"] [--collection-filter="<collection_filter>"] [--scan-events-mode=<mode>] [--force-reporting] [--beta]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Replay - Status
### Warnings

> 

### Syntax

> `tool task replay status [--project=<project_id>] [--running] [--filter=<filter>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Vacuum Redshift - Run
### Warnings

> 

### Syntax

> `tool task redshift-vacuum run --workspace=<workspace> [--query-slots=<number>] [--enable-deep-copy=<bool>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Vacuum Redshift - Status
### Warnings

> 

### Syntax

> `tool task redshift-vacuum status [--running] [--filter=<filter>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Redshift Migration Validator
### Warnings

> 

### Syntax

> `tool task redshift-validate-v1-v3 --workspace=<workspace>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Redshift Version Validator
### Warnings

> 

### Syntax

> `tool task redshift-validate --workspace=<workspace> --old-hostname=<v> --old-user=<v> --old-password=<v> --old-database=<v> --new-hostname=<v> --new-user=<v> --new-password=<v> --new-database=<v>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Redshift Migration Status
### Warnings

> 

### Syntax

> `tool task redshift-migrate-status`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Redshift Migrate
### Warnings

> 

### Syntax

> `tool task redshift-migrate --old-hostname=<v> --old-user=<v> --old-password=<v> --old-database=<v> --new-hostname=<v> --new-user=<v> --new-password=<v> --new-database=<v> --schema=<schema> --tables=<tables> --s3-bucket=<s3_bucket> --s3-bucket-region=<s3_bucket_region> --drop=<drop> --max-errors=<max_errors> [--offset=<offset> --concurrency-level=<concurrency_level>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Redshift Events - Range
### Warnings

> 

### Syntax

> `tool task redshift-range-events --workspace=<workspace>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Redshift Schema
### Warnings

> 

### Syntax

> `tool task redshift-schema --workspace=<workspace> [--match-schemas] [--match-columns] [--match-tables] [--match-column-types] [--force-column-types] [--project=<project_ids>...]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Events Index Backfill
### Warnings

> 

### Syntax

> `tool task events-index-backfill --workspace=<workspace>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Scan Users
### Warnings

> 

### Syntax

> `tool task scan-users --workspace=<workspace> [--publish-objects] [--publish-users] [--from=<from>] [--to=<to>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Task Logs
### Warnings

> 

### Syntax

> `tool task logs <id> [--tail=<tail>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Task Scheduler
### Warnings

> 

### Syntax

> `tool task scheduler [--tail=<tail>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Task Describe
### Warnings

> 

### Syntax

> `tool task describe <id> [--tail=<tail>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Task Stop
### Warnings

> 

### Syntax

> `tool task stop <id>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Source Logs
### Warnings

> 

### Syntax

> `tool task source-logs <s3_log_path>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: ECS Logs
### Warnings

> 

### Syntax

> `tool task ecs-logs <task_arn> [--raw]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: PSQL
### Warnings

> 

### Syntax

> `tool psql <workspace>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: PGCLI - pretty PSQL
### Warnings

> 

### Syntax

> `tool pgcli <workspace>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Get User
### Warnings

> 

### Syntax

> `tool user get --email=<email> --workspace=<workspace>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: User Backfill Counts
### Warnings

> 

### Syntax

> `tool user backfill-counts --workspace=<workspace> --from=<from> --to=<to>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Events Scan
### Warnings

> 

### Syntax

> `tool events scan --project=<project> --from=<from> --type=<type> [--to=<to>] [--collection=<collection>] [--count-only]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Billing Scan
### Warnings

> 

### Syntax

> `tool billing scan --workspace=<id> --period=<period>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Add Custom Salesforce Objects
### Warnings

> 

### Syntax

> `tool source salesforce custom-object --id=<id> [--add=<object>...] [--remove=<remove>...]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Set Connector Frequency
### Warnings

> 

### Syntax

> `tool warehouse custom-frequency --workspace=<workspace> <duration>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Get Object
### Warnings

> 

### Syntax

> `tool object get [--source=<source>] --project-id=<project> --collection=<collection> --id=<id>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Warehouse Properties Blacklist
### Warnings

> 

### Syntax

> `tool schema disable-properties (--workspace=<workspace_slug> |  --project=<project_ids>...) --source=<source_id> --collection-regex=<collection_regex> --regex=<property_regex> [--dry-run] [--exclude=<exclude_property_name>....] [--enable]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Warehouse Collection Blacklist
### Warnings

> 

### Syntax

> `tool schema disable-collections (--workspace=<workspace_slug> |  --project=<project_ids>...) --source=<source_id> --collection-regex=<collection_regex> [--dry-run]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Delete Schema
### Warnings

> 

### Syntax

> `tool schema delete --project=<project_id> --source=<source_id>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Cleanup - Reports
### Warnings

> 

### Syntax

> `tool cleanup reports (connectors | sources) --workspace=<workspace_slug> [--from=<from>]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Cleanup - Database
### Warnings

> 

### Syntax

> `tool cleanup database (--workspace=<workspace_slug> |  --project=<project_ids>...)`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Cleanup - Tables
### Warnings

> 

### Syntax

> `tool cleanup tables (--workspace=<workspace_slug> |  --project=<project_ids>...) --from=<from> --to=<to> [--table=<table>...]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Cleanup - Warehouse Billing
### Warnings

> 

### Syntax

> `tool cleanup warehouse-billing --workspace=<workspace_slug> --from=<from>`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Tool Help

### Syntax

> `tool -h | --help`

###### last updated: Jun 30, 2016

_______________


## Title: Tool Version

### Syntax

> `tool --version`

###### last updated: Jun 30, 2016

_______________

