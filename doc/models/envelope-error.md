
# Envelope Error

The error context. `code` is a stable descriptor in all-caps from a closed
set per endpoint. `message` is a human-readable summary of what went wrong.

*This model accepts additional fields of type unknown.*

## Structure

`EnvelopeError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string` | Required | The error code. |
| `message` | `string` | Required | The error message. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { EnvelopeError } from 'sz-apimatic-sdk';

const envelopeError: EnvelopeError = {
  code: 'code2',
  message: 'message4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

