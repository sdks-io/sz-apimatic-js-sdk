
# List Records Response

*This model accepts additional fields of type unknown.*

## Structure

`ListRecordsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hasMore` | `boolean \| undefined` | Optional | True when limit or the byte budget cut the page short. Page forward with<br>since = records\[last\].record_id.<br><br>**Default**: `false` |
| `records` | [`Record[] \| undefined`](../../doc/models/record.md) | Optional | Oldest first. A short page is normal: a page ends at limit or at a byte<br>budget, whichever binds first. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ListRecordsResponse } from 'sz-apimatic-sdk';

const listRecordsResponse: ListRecordsResponse = {
  hasMore: false,
  records: [
    {}
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

