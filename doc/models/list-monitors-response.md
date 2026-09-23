
# List Monitors Response

*This model accepts additional fields of type unknown.*

## Structure

`ListMonitorsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hasMore` | `boolean \| undefined` | Optional | True when limit or the byte budget cut the page short. Page forward with<br>before = monitors\[last\].monitor_id.<br><br>**Default**: `false` |
| `monitors` | [`Monitor[] \| undefined`](../../doc/models/monitor.md) | Optional | Newest first. A short page is normal: a page ends at limit or at a byte<br>budget, whichever binds first. A monitor carries its whole request list,<br>so a count alone cannot bound the response. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ListMonitorsResponse } from 'sz-apimatic-sdk';

const listMonitorsResponse: ListMonitorsResponse = {
  hasMore: false,
  monitors: [
    {}
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

