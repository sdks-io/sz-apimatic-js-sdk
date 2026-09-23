
# Record

*This model accepts additional fields of type unknown.*

## Structure

`Record`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `searchResult` | [`SearchRecord`](../../doc/models/search-record.md) | Required | - |
| `firstSeenAt` | `string \| null \| undefined` | Optional | - |
| `recordId` | `string \| undefined` | Optional | **Default**: `'0'` |
| `runId` | `string \| undefined` | Optional | **Default**: `'0'` |
| `type` | [`RecordType`](../../doc/models/record-type.md) | Required | **Default**: `RecordType.SearchResult` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Record, RecordType } from 'stz-apimatic-sdk';

const record: Record = {
  searchResult: {
    document: null,
    matchedRequests: [
      {}
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  type: RecordType.SearchResult,
  firstSeenAt: 'first_seen_at0',
  recordId: '0',
  runId: '0',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

