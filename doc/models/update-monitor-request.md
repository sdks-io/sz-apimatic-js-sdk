
# Update Monitor Request

*This model accepts additional fields of type unknown.*

## Structure

`UpdateMonitorRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cadence` | `string` | Required | - |
| `apiKey` | `string \| null \| undefined` | Optional | - |
| `monitorId` | `string \| undefined` | Optional | - |
| `name` | `string \| null \| undefined` | Optional | - |
| `searchRequests` | [`SearchRequest[] \| undefined`](../../doc/models/search-request.md) | Optional | Replaces the list wholesale when set. An empty list is read as "not set"<br>and keeps the current requests. A request keeps its id and its health when<br>every field of its body is unchanged. |
| `status` | [`MonitorStatus \| undefined`](../../doc/models/monitor-status.md) | Optional | - |
| `webhook` | [`Webhook1 \| null \| undefined`](../../doc/models/webhook-1.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { MonitorStatus, UpdateMonitorRequest } from 'stz-apimatic-sdk';

const updateMonitorRequest: UpdateMonitorRequest = {
  cadence: 'cadence8',
  apiKey: 'api_key2',
  monitorId: 'monitor_id8',
  name: 'name0',
  searchRequests: [
    {}
  ],
  status: MonitorStatus.Active,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

