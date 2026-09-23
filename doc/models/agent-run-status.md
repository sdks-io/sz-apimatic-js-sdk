
# Agent Run Status

Where a run is in its lifecycle:
pending → running → completed / failed / cancelled.

## Enumeration

`AgentRunStatus`

## Fields

| Name |
|  --- |
| `Pending` |
| `Running` |
| `Completed` |
| `Failed` |
| `Cancelled` |

## Example

```ts
import { AgentRunStatus } from 'stz-apimatic-sdk';

const agentRunStatus = AgentRunStatus.Pending;
```

