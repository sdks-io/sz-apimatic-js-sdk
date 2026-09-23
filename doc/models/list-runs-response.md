
# List Runs Response

*This model accepts additional fields of type unknown.*

## Structure

`ListRunsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hasMore` | `boolean \| undefined` | Optional | True when limit cut the page short.<br><br>**Default**: `false` |
| `runs` | [`Run[] \| undefined`](../../doc/models/run.md) | Optional | Newest first by default, so \[0\] is the latest run. Page back with<br>before = runs\[last\].run_id; pass sort = SORT_ORDER_ASC to walk forward<br>instead, and page with since = runs\[last\].run_id. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ListRunsResponse } from 'stz-apimatic-sdk';

const listRunsResponse: ListRunsResponse = {
  hasMore: false,
  runs: [
    {},
    {
      status: null,
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

