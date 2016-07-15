## Title: Info
### Warnings

>

### Syntax

> `tool info <target> <target-id>`

#### Parameters:

__target__
	What you would like information on. Possible values: workspace, warehouse, project

__target-id__
	The slug or ID of the target you'd like info on:
	* workspace: slug or ID
	* warehouse: slug or ID
	* project: ID

#### Return Value:
	Returns an object with relevant information about the target.

### Examples

```
t info workspace segment

t info warehouse OmLu2v3BEm

t info project 9K2CM0i1h4

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

__target__
	What you would like to check the status of:
	* source
	* conneector
	* workspace: slug

__running__
	Optional. Allows you to filter by what is currently running.

__failed__
	Optional. Allows you to filter by what failed.

__hanging__
	Optional. Allows you to filter by what is hanging.

__tail__
	Optional.

__kill__
	Optional.


#### Return Value:
	Will return a list of objects, broken out by source.

### Example:

```
t task status --workspace=segment --running


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

__workspace__
	Workspace slug.

__force__
	Optional. This flag will stop any sync that is currently running for the source and start a new one.

__option__
	Optional.

#### Return Value:

### Example:

```
t task force-run source --workspace=segment --force
```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Warehouse Connector - Run
### Warnings

> If this command is run with the --force flag and a sync is currently running, it will stop the sync and an the following error message will appear in the UI for that run: "Application terminated"

### Syntax

> `tool task force-run connector (--workspace=<workspace_slug> | --project=<project_ids>...) [--force] [--option=<options>...]`

#### Parameters:

__target__
	* workspace: slug
	* project: id

__force__
	Optional. This flag will stop any sync that is currently running for the source and start a new one.

__option__
	Optional.
	* REPLAY_MODE: full or range
	* REPLAY_FROM: "YYYY-MM-DD"
	* REPLAY_TO: "YYYY-MM-DD"
	* SOURCE_FILTER: objects or events
	* COLLECTION_FILTER: table name
		* you can select multiple tables with the following syntax: "\(table_one\|table_two\|table_three\)"


#### Return Value:
	Object with run info.

### Example:

```
t task force-run connector --project=GroKT0tUsy --force

t task force-run connector --option=REPLAY_MODE=full --option=SOURCE_FILTER=objects --option=COLLECTION_FILTER=users --workspace=segment --force

t task force-run connector --option=SOURCE_FILTER=events --option=COLLECTION_FILTER="\(tracks\|data_sent\|identifies\)" --project=GroKT0tUsy --force
```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Replay - Run
### Warnings

> This will run backfills on the expiramental connector. Be aware of how many containers are currently being used before running. If you run this command for a workspace, it will allocate max-containers to EACH source. For example if you have 10 sources, and run the command with --max-containers=20, you will use 200 containers.

At the moment, the expiramental connector will only work on events, not objects.

### Syntax

> `tool task replay run (--workspace=<workspace_id> | --project=<project_id> ) (--full | --from=<from> --to=<to>) [--cluster-id=<cluster_id>] [--max-containers=<max_containers>] [--exclude-project=<exclude_project>...] [--max-error="<max_error>"] [--notify="<notify>"] [--collection-filter="<collection_filter>"] [--scan-events-mode=<mode>] [--force-reporting] [--beta]`

#### Parameters:

__target__
	* workspace: slug
	* project: id

__range__
	* full
	* from: YYYY-MM-DD
	* to: YYYY-MM-DD

__cluster-id__
	Optional.

__max-containers__
	Optional. Integer. Default is 30.

__exclude-project__
	Optional.

__max-error__
	Optional.

__notify__
	Optional. Slack username. Replays run on the expiraental connector will post when they start and finish in the #alerts-replay channel. This flag will @slack_username in the channel when the replay starts and finishes.

__collection-filter__
	Optional. Table name.

__scan-events-mode__
	Optional.

__force-reporting__
	Optional.

__beta__
	Optional.


#### Return Value:
	Object with run info.

### Example:

```
t task replay run --workspace=segment --from=2016-01-01 --to=2016-02-15 --max-containers=5

t task replay run --project=GroKT0tUsy --full --notify=noonan

```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Replay - Status
### Warnings

> This will give you the status of backfills that were run on the expiramental connector.

### Syntax

> `tool task replay status [--project=<project_id>] [--running] [--filter=<filter>]`

#### Parameters:

__project__
	Optional. Source ID.

__running__
	Optional.

__filter__
	Optional.

#### Return Value:
	List of objects with backfill info.

### Example:

```
t task replay status

t task replay status --project=GroKT0tUsy
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

__workspace__
	Workspace slug

__query-slots__
	Optional. Integer

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
