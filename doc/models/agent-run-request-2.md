
# Agent Run Request 2

The request the run was created with.

*This model accepts additional fields of type unknown.*

## Structure

`AgentRunRequest2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `effort` | `string \| null \| undefined` | Optional | The effort level the run executes at: the request's `effort`, or the<br>default level when it named none. |
| `outputSchema` | `unknown \| null \| undefined` | Optional | The request's `output_schema`, when one was given. On gRPC the object is<br>JSON-encoded. |
| `query` | `string \| undefined` | Optional | The natural-language question. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AgentRunRequest2 } from 'sz-apimatic-sdk';

const agentRunRequest2: AgentRunRequest2 = {
  effort: 'effort8',
  outputSchema: { 'key1': 'val1', 'key2': 'val2' },
  query: 'query8',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

