
# Create Monitor Request

*This model accepts additional fields of type unknown.*

## Structure

`CreateMonitorRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cadence` | `string` | Required | - |
| `apiKey` | `string \| null \| undefined` | Optional | - |
| `name` | `string \| undefined` | Optional | Unique per org among live monitors; a deleted monitor's name becomes<br>available again. At most 512 bytes of UTF-8. |
| `searchRequests` | [`SearchRequest[] \| undefined`](../../doc/models/search-request.md) | Optional | At least one, at most 1000. Every request runs on every run. A request<br>with an `api_key` set, a blank `query`, or a body identical to another in<br>the list is rejected. |
| `status` | [`MonitorStatus2 \| undefined`](../../doc/models/monitor-status-2.md) | Optional | - |
| `webhook` | [`Webhook \| null \| undefined`](../../doc/models/webhook.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateMonitorRequest, MonitorStatus2 } from 'stz-apimatic-sdk';

const createMonitorRequest: CreateMonitorRequest = {
  cadence: 'cadence2',
  apiKey: 'api_key2',
  name: 'name0',
  searchRequests: [
    {}
  ],
  status: MonitorStatus2.Active,
  webhook: null,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

