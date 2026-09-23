
# Run Request

One run's outcome for one search request.

*This model accepts additional fields of type unknown.*

## Structure

`RunRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `completedAt` | `string \| null \| undefined` | Optional | - |
| `newRecords` | `bigint \| undefined` | Optional | **Default**: `0`<br><br>**Constraints**: `>= 0` |
| `reason` | `string \| undefined` | Optional | Why the request failed, empty when it succeeded. Not machine-readable. |
| `requestId` | `string \| undefined` | Optional | - |
| `resultsReturned` | `bigint \| undefined` | Optional | **Default**: `0`<br><br>**Constraints**: `>= 0` |
| `status` | [`RequestStatus`](../../doc/models/request-status.md) | Required | **Default**: `RequestStatus.Ok` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RequestStatus, RunRequest } from 'sz-apimatic-sdk';

const runRequest: RunRequest = {
  status: RequestStatus.Ok,
  completedAt: 'completed_at0',
  newRecords: BigInt(0),
  reason: 'reason6',
  requestId: 'request_id0',
  resultsReturned: BigInt(0),
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

