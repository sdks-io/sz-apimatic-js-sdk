
# Monitor

*This model accepts additional fields of type unknown.*

## Structure

`Monitor`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cadence` | `string` | Required | - |
| `createdAt` | `string \| null \| undefined` | Optional | - |
| `monitorId` | `string \| undefined` | Optional | - |
| `name` | `string \| undefined` | Optional | - |
| `searchRequests` | [`MonitorSearchRequest[] \| undefined`](../../doc/models/monitor-search-request.md) | Optional | - |
| `status` | [`MonitorStatus`](../../doc/models/monitor-status.md) | Required | **Default**: `MonitorStatus.Active` |
| `updatedAt` | `string \| null \| undefined` | Optional | - |
| `webhook` | [`Webhook \| null \| undefined`](../../doc/models/webhook.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Monitor, MonitorStatus } from 'sz-apimatic-sdk';

const monitor: Monitor = {
  cadence: 'cadence6',
  status: MonitorStatus.Active,
  createdAt: 'created_at2',
  monitorId: 'monitor_id2',
  name: 'name4',
  searchRequests: [
    {}
  ],
  updatedAt: 'updated_at0',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

