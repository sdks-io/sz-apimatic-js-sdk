
# List Run Requests Response

*This model accepts additional fields of type unknown.*

## Structure

`ListRunRequestsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requests` | [`RunRequest[] \| undefined`](../../doc/models/run-request.md) | Optional | Ordered by request_id. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ListRunRequestsResponse } from 'stz-apimatic-sdk';

const listRunRequestsResponse: ListRunRequestsResponse = {
  requests: [
    {},
    {
      status: null,
    },
    {
      status: null,
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

