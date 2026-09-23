
# Payload

*This model accepts additional fields of type unknown.*

## Structure

`Payload`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `searchResult` | [`SearchRecord`](../../doc/models/search-record.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Payload } from 'stz-apimatic-sdk';

const payload: Payload = {
  searchResult: {
    document: null,
    matchedRequests: [
      {}
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

