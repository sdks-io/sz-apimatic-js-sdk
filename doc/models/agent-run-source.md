
# Agent Run Source

One source a run cited.

*This model accepts additional fields of type unknown.*

## Structure

`AgentRunSource`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `number \| undefined` | Optional | Identifier within the run, cited as `\[id\]` in `text` and as `source_id`<br>in `grounding`.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0` |
| `url` | `string \| undefined` | Optional | URL of the source document. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AgentRunSource } from 'sz-apimatic-sdk';

const agentRunSource: AgentRunSource = {
  id: 0,
  url: 'url0',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

