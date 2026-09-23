
# Agent Run Output

A run's output.

*This model accepts additional fields of type unknown.*

## Structure

`AgentRunOutput`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grounding` | [`AgentRunGrounding[] \| undefined`](../../doc/models/agent-run-grounding.md) | Optional | Per-field citations for `structured`. Empty when there is no structured<br>output. |
| `sources` | [`AgentRunSource[] \| undefined`](../../doc/models/agent-run-source.md) | Optional | The sources cited by `text` or `grounding`, numbered in order of first<br>citation. |
| `structured` | `unknown \| null \| undefined` | Optional | Structured result shaped by the request's `output_schema`. Unset when the<br>request had none. Fields that could not be grounded are expected to be<br>null. On gRPC the object is JSON-encoded. |
| `text` | `string \| null \| undefined` | Optional | Cited markdown report. Inline `\[n\]` markers cite the entry of `sources`<br>whose `id` is `n`. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AgentRunOutput } from 'stz-apimatic-sdk';

const agentRunOutput: AgentRunOutput = {
  grounding: [
    {},
    {
    }
  ],
  sources: [
    {}
  ],
  structured: { 'key1': 'val1', 'key2': 'val2' },
  text: 'text6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

