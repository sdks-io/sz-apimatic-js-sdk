
# Search Record

*This model accepts additional fields of type unknown.*

## Structure

`SearchRecord`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `document` | [`Document \| null \| undefined`](../../doc/models/document.md) | Optional | - |
| `matchedRequests` | [`SearchRequestRef[] \| undefined`](../../doc/models/search-request-ref.md) | Optional | Only the requests that matched in the run that emitted this record. A record<br>is emitted once, on first sight, so a request that would match it in a later<br>run never attaches to it. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { SearchRecord } from 'stz-apimatic-sdk';

const searchRecord: SearchRecord = {
  document: null,
  matchedRequests: [
    {}
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

