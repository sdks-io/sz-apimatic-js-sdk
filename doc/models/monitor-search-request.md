
# Monitor Search Request

A search request stored on a monitor, with its server-assigned id.

*This model accepts additional fields of type unknown.*

## Structure

`MonitorSearchRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `consecutiveFailures` | `bigint \| undefined` | Optional | Consecutive failed runs for this request.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0` |
| `lastSuccessAt` | `string \| null \| undefined` | Optional | - |
| `request` | [`SearchRequest \| null \| undefined`](../../doc/models/search-request.md) | Optional | - |
| `requestId` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { MonitorSearchRequest } from 'stz-apimatic-sdk';

const monitorSearchRequest: MonitorSearchRequest = {
  consecutiveFailures: BigInt(0),
  lastSuccessAt: 'last_success_at6',
  request: null,
  requestId: 'request_id4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

