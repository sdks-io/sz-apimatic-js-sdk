
# Update Monitor Response

*This model accepts additional fields of type unknown.*

## Structure

`UpdateMonitorResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitor` | [`Monitor \| null \| undefined`](../../doc/models/monitor.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { UpdateMonitorResponse } from 'stz-apimatic-sdk';

const updateMonitorResponse: UpdateMonitorResponse = {
  monitor: null,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

