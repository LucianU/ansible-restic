# restic
A role that sets up [restic]. It:
* installs restic
* creates a directory that holds the `restic` repo. In `restic` terminology, a repo is a directory that `restic` backs up.
* initializes the remote repo
* sets up cron jobs to perform backups

Role Variables
--------------
| Variable | Description | Default value |
|----------|-------------|---------------|
| `restic_config_dir` | Path to where restic holds configuration for all repos on the machine | `/etc/restic` |
| `restic_dir_to_backup` | Path to the dir that `restic` will backup | `none` |
| `restic_repo_config_dir` | Path to the config dir of a specific repo | `{{ restic_config_dir }}/{{ restic_repo_name }}` |
| `restic_repo_config` | Path to the config for a specific repo | `{{ restic_repo_config_dir }}/env` |
| `restic_repo_name` | Name of a specific repo we're enabling backups for | `none` |
| `restic_repo_access_key` | Access key to S3-compatible storage service | `none` |
| `restic_repo_access_key_secret` | Access key secret to S3-compatible storage service | `none` |
| `restic_repo_endpoint` | Endpoint of S3-compatible storage service. Format `s3:[region].[domain]/[bucket-name]`. Example `s3:fra1.digitaloceanspaces.com/restic-backup` | `none` |
| `restic_repo_password` | Password for `restic` remote repo | `none` |

[restic]: https://restic.net/
