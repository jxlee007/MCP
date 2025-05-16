# n8n-data Directory Structure

This directory contains data files for the n8n workflow automation system and related services.

## Folder Structure

| Directory/File | Description |
|----------------|-------------|
| **n8n/** | Main n8n application data |
| &nbsp;&nbsp;├── config | Configuration files for n8n |
| &nbsp;&nbsp;├── crash.journal | Log of any n8n crashes |
| &nbsp;&nbsp;├── database.sqlite | SQLite database file for n8n |
| &nbsp;&nbsp;├── n8nEventLog*.log | Event log files for monitoring n8n activities |
| &nbsp;&nbsp;├── binaryData/ | Storage for binary data used in workflows |
| &nbsp;&nbsp;├── git/ | Git integration data |
| &nbsp;&nbsp;├── nodes/ | Custom node files |
| &nbsp;&nbsp;└── ssh/ | SSH configuration for remote connections |
| **pg-vector/** | PostgreSQL vector database storage |
| **yt/** | YouTube data storage (for workflows related to YouTube) |

## Usage Notes

- The `n8n/` directory contains all the core n8n data including workflows, credentials, and execution logs
- The `pg-vector/` directory stores vector embeddings for AI functionality
- The `yt/` directory is dedicated to YouTube data processing workflows

## Maintenance

### Backup Recommendations
- Regularly backup the `database.sqlite` file as it contains all workflow configurations
- Consider implementing a cron job to back up the entire `n8n-data` directory

### Troubleshooting
- Check `crash.journal` and log files in case of workflow execution failures
- Ensure proper permissions on all directories for the Docker containers to access them

## Related Components
- This data directory is used by the services defined in `docker-compose.yml`
- See main documentation for more information on configuring these services