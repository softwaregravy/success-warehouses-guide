## Title: Info
### Warnings

>

### Syntax

> `tool info <target> <target-id>`

#### Parameters:

_target_
What you would like information on. Possible values: workspace, warehouse, project

_target-id_
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

###### last updated: Sept 5, 2016

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

_target_
What you would like to check the status of:
* source
* connector
* workspace: slug

_running_
Optional. Allows you to filter by what is currently running.

_failed_
Optional. Allows you to filter by what failed.

_hanging_
Optional. Allows you to filter by what is hanging.

_tail_
Optional.

_kill_
Optional.


#### Return Value:
Will return a list of objects, broken out by source.

### Example:

```
t task status --workspace=segment --running

```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Source Runner - Run
### Warnings

>

### Syntax

> `tool task force-run source --workspace=<workspace_slug> [--force] [--option=<options>...]`

#### Parameters:

_workspace_
Workspace slug.

_force_
Optional. This flag will stop any sync that is currently running for the source and start a new one.

_option_
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

_target_
* workspace: slug
* project: id

_force_
Optional. This flag will stop any sync that is currently running for the source and start a new one.

_option_
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

###### last updated: Sept 5, 2016

_______________


## Title: Replay - Run
### Warnings

> This will run backfills on the expiramental connector. Be aware of how many containers are currently being used before running. If you run this command for a workspace, it will allocate max-containers to EACH source. For example if you have 10 sources, and run the command with --max-containers=20, you will use 200 containers.

At the moment, the expiramental connector will only work on events, not objects.

### Syntax

> `tool task replay run (--workspace=<workspace_id> | --project=<project_id> ) (--full | --from=<from> --to=<to>) [--cluster-id=<cluster_id>] [--max-containers=<max_containers>] [--exclude-project=<exclude_project>...] [--max-error="<max_error>"] [--notify="<notify>"] [--collection-filter="<collection_filter>"] [--scan-events-mode=<mode>] [--force-reporting] [--beta]`

#### Parameters:

_target_
* workspace: slug
* project: id

_range_
* full
* from: YYYY-MM-DD
* to: YYYY-MM-DD

_cluster-id_
Optional.

_max-containers_
Optional. 
Integer. Default is 30.

_exclude-project_
Optional.

_max-error_
Optional.

_notify_
Optional. 
Slack username. Replays run on the expiraental connector will post when they start and finish in the #alerts-replay channel. This flag will @slack_username in the channel when the replay starts and finishes.

_collection-filter_
Optional. 
Table name.

_scan-events-mode_
Optional.

_force-reporting_
Optional.

_beta_
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

###### last updated: Sept 5, 2016

_______________


## Title: Replay - Status
### Warnings

> This will give you the status of backfills that were run on the expiramental connector.

### Syntax

> `tool task replay status [--project=<project_id>] [--running] [--filter=<filter>]`

#### Parameters:

_project_
Optional. 
Source ID.

_running_
Optional.

_filter_
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

###### last updated: Sept 5, 2016

_______________


## Title: Vacuum Redshift - Run
### Warnings

>

### Syntax

> `tool task redshift-vacuum run --workspace=<workspace> [--query-slots=<number>] [--enable-deep-copy=<bool>]`

#### Parameters:

_workspace_
Workspace slug

_query-slots_
Optional. 
Integer

#### Return Value:
Object with vacuum info

### Example:

```
t task redshift-vacuum run --workspace=segment
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Vacuum Redshift - Status
### Warnings

>

### Syntax

> `tool task redshift-vacuum status [--running] [--filter=<filter>]`

#### Parameters:

_running_ Optional.

_filter_ Optional.

#### Return Value:
List of currently running vacuums and their relevant info

### Example:

```
t task redshift-vacuum status
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Redshift Migration Validator
### Warnings

>

### Syntax

> `tool task redshift-validate-v1-v3 --workspace=<workspace>`

#### Parameters:

_workspace_
Workspace slug

#### Return Value:
Object with relevant info and a report will be generated in the alerts-rs-validator slack channel
### Example:

```
t task redshift-validate-v1-v3 --workspace=segment
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Redshift Version Validator
### Warnings

>

### Syntax

> `tool task redshift-validate --workspace=<workspace> --old-hostname=<v> --old-user=<v> --old-password=<v> --old-database=<v> --new-hostname=<v> --new-user=<v> --new-password=<v> --new-database=<v>`

#### Parameters:
_workspace_
Workspace slug

_old-hostname_
Original cluster hostname

_old-user_
Original cluster user

_old-password_
Original cluster password

_old-database_
Original DB name

_new-hostname_
New cluster hostname

_new-user_
New cluster user

_new-password_
New cluster password

_new-database_
New DB name

#### Return Value:
Object with relevant info and a report will be generated in the alerts-rs-validator slack channel

### Example:

```

```

#### How to find it:
To find the relevant cluster information, you can use `t info warehouse <slug>`.

#### See Also:

###### last updated: Sept 5, 2016

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

_workspace_
Workspace slug

_project_ Optional.
Project ID

#### Return Value:
Object with relevant info.

### Example:

```
t task redshift-schema --workspace=segment --match-columns

t task redshift-schema --workspace=segment --match-schemas
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Events Index Backfill
### Warnings

>

### Syntax

> `tool task events-index-backfill --workspace=<workspace>`

#### Parameters:

_workspace_
Workspace slug

#### Return Value:

### Example:

```
t task events-index-backfill --workspace=segment
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Scan Users
### Warnings

>

### Syntax

> `tool task scan-users --workspace=<workspace> [--publish-objects] [--publish-users] [--from=<from>] [--to=<to>]`

#### Parameters:

_workspace_
Workspace slug

_from_ Optional.
YYYY-MM-DD

_to_ Optional.
YYYY-MM-DD

#### Return Value:

### Example:

```
t task scan-users --workspace=segment

t task scan-users --workspace=segment --from=2016-01-01 --to=2016-09-01
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

_id_
Task ID

_tail_ Optional.
Integer

#### Return Value:
Logs for the task

### Example:

```
t task logs arn:aws:ecs:us-west-2:752180062774:task/350a73af-b9c0-4beb-a704-7a13b4d804b6 --tail=10
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

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

_id_
Task ID

#### Return Value:

### Example:

```
t task stop arn:aws:ecs:us-west-2:752180062774:task/350a73af-b9c0-4beb-a704-7a13b4d804b6
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

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

_task-arn_
Task Id

#### Return Value:

### Example:

```
t task ecs-logs arn:aws:ecs:us-west-2:752180062774:task/350a73af-b9c0-4beb-a704-7a13b4d804b6
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

_workspace_
Slug

#### Return Value:
Prompt to which warehouse you'd like to login to.

### Example:

```
t psql segment
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: PGCLI - pretty PSQL
### Warnings

>

### Syntax

> `tool pgcli <workspace>`

#### Parameters:

_workspace_
Slug

#### Return Value:
Prompt to which warehouse you'd like to login to.

### Example:

```
t pgcli segment
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

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

>No longer available

### Syntax

> `tool events scan --project=<project> --from=<from> --type=<type> [--to=<to>] [--collection=<collection>] [--count-only]`

#### Parameters:

#### Return Value:

### Example:

```

```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

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

_id_
Source ID

_add_ Optional.
Custom object name

_remove_ Optional.
Custom object name.

#### Return Value:
List of all the custom object associated with the source.
### Example:

```
t source salesforce custom-object --id=12345678 --add=Lead_Request__c --add=Domain__c
```

#### How to find it:
You can get the source ID from the Zendesk side bar, the UI or Hermes

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Set Connector Frequency
### Warnings

>

### Syntax

> `tool warehouse custom-frequency --workspace=<workspace> <duration>`

#### Parameters:

_workspace_
Workspace slug.

_duration_
Integer followed by metric 

#### Return Value:

### Example:

```
t warehouse custom-frequency --workspace=segment 1h

t warehouse custom-frequency --workspace=segment 30m
```

#### How to find it:

#### See Also:

###### last updated: Jun 30, 2016

_______________


## Title: Get Object
### Warnings

>

### Syntax

> `tool object get --project-id=<project> --collection=<collection> --id=<id>`

#### Parameters:

_project-id_
Source ID

_collection_
Collection or table name

_id_
ID of the object

#### Return Value:

### Example:

```
t object get --project-id=12345678 --collection=invoices --id=in_18apt12WxDQT5z9j
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Warehouse Properties Blacklist
### Warnings

>You must append `--dry-run` when first running this to see what you will be blacklisting.

### Syntax

> `tool schema disable-properties (--workspace=<workspace_slug> |  --project=<project_ids>...) --source=<source_id> --collection-regex=<collection_regex> --regex=<property_regex> [--dry-run] [--exclude=<exclude_property_name>....] [--enable]`

#### Parameters:

_workspace_
Workspace Slug

_project_
Source ID.

_source_
Source info. 
If you are blacklisting an event property, the value will be `events`.
If you are blacklisting an object property, you'll have check infra-mongo for this.

_collection-regex_
Regex pattern of the table with the properties you'd like to blacklist.

_regex_
Regex pattern of the properties you'd like to blacklist.

_dry-run_
Flag that allows you to see what will be blacklisted before you make the change.

_exclude_ Optional.
Properites you'd like to exclude from the regex pattern.

_enable_ Optional.
Flag to re-enable properties that have been blacklisted.

#### Return Value:
List of properties that were blacklisted

### Example:

```
t schema disable-properties --project=gy2d --source=events --collection-regex="tracks" --regex="context_traits_*" --dry-run

t schema disable-properties --workspace=segment --source=projects --collection-regex=".*" --regex="context_traits_*" --dry-run
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

_______________


## Title: Warehouse Collection Blacklist
### Warnings

>

### Syntax

> `tool schema disable-collections (--workspace=<workspace_slug> |  --project=<project_ids>...) --source=<source_id> --collection-regex=<collection_regex> [--dry-run]`

#### Parameters:

_workspace_
Workspace Slug

_project_
Source ID.

_source_
Source info. 
If you are blacklisting an event property, the value will be `events`.
If you are blacklisting an object property, you'll have check infra-mongo for this.

_collection-regex_
Regex pattern of the table with the properties you'd like to blacklist.

_dry-run_
Flag that allows you to see what will be blacklisted before you make the change.

#### Return Value:
List of properties that were blacklisted

### Example:

```
t schema disable-collections --workspace=segment --source=evnets --collection-regex="tracks" --dry-run
```

#### How to find it:

#### See Also:

###### last updated: Sept 5, 2016

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
