
# Agent Run Citation

One citation supporting a grounded field.

*This model accepts additional fields of type unknown.*

## Structure

`AgentRunCitation`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sourceId` | `number \| undefined` | Optional | `id` of the entry in `sources` this citation points at.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0` |
| `url` | `string \| undefined` | Optional | URL of the cited document. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AgentRunCitation } from 'stz-apimatic-sdk';

const agentRunCitation: AgentRunCitation = {
  sourceId: 0,
  url: 'url6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

