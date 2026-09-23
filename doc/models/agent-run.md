
# Agent Run

An agent run.

*This model accepts additional fields of type unknown.*

## Structure

`AgentRun`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `completedAt` | `string \| null \| undefined` | Optional | When the run reached a terminal state. Unset until then. |
| `createdAt` | `string \| undefined` | Optional | When the run was created, as an ISO 8601 timestamp. |
| `id` | `string \| undefined` | Optional | Unique run id. |
| `object` | `string \| undefined` | Optional | Object type, always "agent.run". |
| `output` | [`AgentRunOutput2 \| null \| undefined`](../../doc/models/agent-run-output-2.md) | Optional | - |
| `request` | [`AgentRunRequest2 \| null \| undefined`](../../doc/models/agent-run-request-2.md) | Optional | - |
| `startedAt` | `string \| null \| undefined` | Optional | When the run started. Unset while pending. |
| `status` | [`AgentRunStatus2 \| undefined`](../../doc/models/agent-run-status-2.md) | Optional | **Default**: `AgentRunStatus2.Pending` |
| `stopReason` | [`AgentRunStopReason2 \| null \| undefined`](../../doc/models/agent-run-stop-reason-2.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AgentRun, AgentRunStatus2 } from 'sz-apimatic-sdk';

const agentRun: AgentRun = {
  completedAt: 'completed_at4',
  createdAt: 'created_at0',
  id: 'id2',
  object: 'object0',
  output: null,
  status: AgentRunStatus2.Pending,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

