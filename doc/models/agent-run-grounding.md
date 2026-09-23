
# Agent Run Grounding

Citations for one field of `output.structured`.

*This model accepts additional fields of type unknown.*

## Structure

`AgentRunGrounding`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `citations` | [`AgentRunCitation[] \| undefined`](../../doc/models/agent-run-citation.md) | Optional | Citations supporting this field's value. |
| `field` | `string \| undefined` | Optional | Dot-notation path into the structured output, e.g. "companies.0.ceo". |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AgentRunGrounding } from 'sz-apimatic-sdk';

const agentRunGrounding: AgentRunGrounding = {
  citations: [
    {},
    {
    },
    {
    }
  ],
  field: 'field8',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

