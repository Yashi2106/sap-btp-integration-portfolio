# Poll Enrich — Multi-Source SFTP Routing

## Project Overview
Designed an iFlow that polls 3 different SFTP source folders, processes files from each, and routes them to separate output folders using conditional router and Poll Enrich pattern. Includes archive functionality for processed files.

## Architecture Diagram

## Technical Details

### SFTP Configuration
| Folder | Path | Purpose |
|:---|:---|:---|
| Input1 | `/inbound/input1/` | Source folder for first data source |
| Input2 | `/inbound/input2/` | Source folder for second data source |
| Input3 | `/inbound/input3/` | Source folder for third data source |
| Output1 | `/outbound/output1/` | Destination for processed files from Input1 |
| Output2 | `/outbound/output2/` | Destination for processed files from Input2 |
| Output3 | `/outbound/output3/` | Destination for processed files from Input3 |
| Archive | `/archive/` | Archive location after successful processing |

### Server Details Used
- Server: `mtsapserver6.themdlabs.com`
- Port: `22`
- Protocol: SFTP

### Key Components Implemented

| Component | Purpose |
|:---|:---|
| **Timer** | Triggers iFlow every 5 minutes |
| **3 SFTP Sender Adapters** | Poll separate input directories |
| **Poll Enrich** | Merges data from all 3 sources |
| **Content Modifier** | Sets exchange property to identify source (Input1/2/3) |
| **Router** | Conditionally routes based on source property |
| **3 SFTP Receiver Adapters** | Write to respective output folders |
| **Move to Archive** | Moves processed files to archive folder |

### Router Conditions
## Testing
- Placed test files in all 3 input folders
- Timer triggered iFlow automatically
- Files moved to correct output folders based on source
- Original files archived after successful processing
- Verified no data mixing between sources

## What I Learned
- Poll Enrich pattern for multi-source data aggregation
- Conditional routing using Router step
- SFTP adapter with move-to-archive configuration
- Security material setup for SFTP username/password
- Exchange properties for maintaining context across iFlow

## Related Skills
- Poll Enrich pattern
- Router (conditional routing)
- SFTP adapters (Sender/Receiver)
- Security Material management
- Timer-based integration
