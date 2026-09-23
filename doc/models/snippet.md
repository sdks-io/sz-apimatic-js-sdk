
# Snippet

One passage selected from a document's body.

*This model accepts additional fields of type unknown.*

## Structure

`Snippet`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `text` | `string \| null \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Snippet } from 'sz-apimatic-sdk';

const snippet: Snippet = {
  text: 'text0',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

