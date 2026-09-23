
# List Agent Runs Response

List-runs response: one page of runs.

*This model accepts additional fields of type unknown.*

## Structure

`ListAgentRunsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `next` | `string \| null \| undefined` | Optional | Cursor to the next page. Unset on the last page. |
| `runs` | [`AgentRun[] \| undefined`](../../doc/models/agent-run.md) | Optional | The page's runs, newest first. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ListAgentRunsResponse } from 'stz-apimatic-sdk';

const listAgentRunsResponse: ListAgentRunsResponse = {
  next: 'next6',
  runs: [
    {},
    {
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

