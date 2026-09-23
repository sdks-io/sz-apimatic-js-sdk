
# Get Monitor Response

*This model accepts additional fields of type unknown.*

## Structure

`GetMonitorResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitor` | [`Monitor \| null \| undefined`](../../doc/models/monitor.md) | Optional | - |
| `runState` | [`RunState2`](../../doc/models/run-state-2.md) | Required | **Default**: `RunState2.Idle` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetMonitorResponse, RunState2 } from 'stz-apimatic-sdk';

const getMonitorResponse: GetMonitorResponse = {
  runState: RunState2.Idle,
  monitor: null,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

