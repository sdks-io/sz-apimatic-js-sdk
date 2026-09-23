
# List Run Records Response

*This model accepts additional fields of type unknown.*

## Structure

`ListRunRecordsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hasMore` | `boolean \| undefined` | Optional | True when limit or the byte budget cut the page short. Page forward with<br>since = records\[last\].record_id.<br><br>**Default**: `false` |
| `records` | [`Record[] \| undefined`](../../doc/models/record.md) | Optional | Oldest first. A short page is normal: a page ends at limit or at a byte<br>budget, whichever binds first. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ListRunRecordsResponse } from 'sz-apimatic-sdk';

const listRunRecordsResponse: ListRunRecordsResponse = {
  hasMore: false,
  records: [
    {},
    {
      searchResult: {},
      type: null,
    },
    {
      searchResult: {},
      type: null,
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

