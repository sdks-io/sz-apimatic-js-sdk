
# Create Monitor Response

*This model accepts additional fields of type unknown.*

## Structure

`CreateMonitorResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitor` | [`Monitor \| null \| undefined`](../../doc/models/monitor.md) | Optional | - |
| `webhookSecret` | `string \| undefined` | Optional | Returned once, at create, and never again. Issued whether or not the<br>create supplied a webhook, so keep it. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateMonitorResponse } from 'sz-apimatic-sdk';

const createMonitorResponse: CreateMonitorResponse = {
  monitor: null,
  webhookSecret: 'webhook_secret4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

