
# Envelope Error 1

The error context.

*This model accepts additional fields of type unknown.*

## Structure

`EnvelopeError1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string` | Required | The error code. |
| `message` | `string` | Required | The error message. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { EnvelopeError1 } from 'stz-apimatic-sdk';

const envelopeError1: EnvelopeError1 = {
  code: 'code4',
  message: 'message4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

