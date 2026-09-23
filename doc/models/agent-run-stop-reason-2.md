
# Agent Run Stop Reason 2

Why the run stopped. Set once the run reaches a terminal state.

## Enumeration

`AgentRunStopReason2`

## Fields

| Name |
|  --- |
| `Finished` |
| `BudgetReached` |
| `Timeout` |
| `Cancelled` |
| `InvalidOutput` |
| `InternalError` |

## Example

```ts
import { AgentRunStopReason2 } from 'stz-apimatic-sdk';

const agentRunStopReason2 = AgentRunStopReason2.Finished;
```

