
# Run

*This model accepts additional fields of type unknown.*

## Structure

`Run`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `completedAt` | `string \| null \| undefined` | Optional | - |
| `firstRecordId` | `string \| undefined` | Optional | The lowest `record_id` this run produced. Records are not contiguous; use<br>`record_count` for the count.<br><br>**Default**: `'0'` |
| `lastRecordId` | `string \| undefined` | Optional | The highest `record_id` this run produced. Records are not contiguous; use<br>`record_count` for the count.<br><br>**Default**: `'0'` |
| `monitorId` | `string \| undefined` | Optional | - |
| `recordCount` | `bigint \| undefined` | Optional | **Default**: `0`<br><br>**Constraints**: `>= 0` |
| `requestsFailed` | `bigint \| undefined` | Optional | **Default**: `0`<br><br>**Constraints**: `>= 0` |
| `requestsOk` | `bigint \| undefined` | Optional | **Default**: `0`<br><br>**Constraints**: `>= 0` |
| `requestsTotal` | `bigint \| undefined` | Optional | **Default**: `0`<br><br>**Constraints**: `>= 0` |
| `runId` | `string \| undefined` | Optional | **Default**: `'0'` |
| `startedAt` | `string \| null \| undefined` | Optional | - |
| `status` | [`RunStatus`](../../doc/models/run-status.md) | Required | **Default**: `RunStatus.Completed` |
| `statusReason` | `string \| undefined` | Optional | Prose for a human, empty when completed. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Run, RunStatus } from 'stz-apimatic-sdk';

const run: Run = {
  status: RunStatus.Completed,
  completedAt: 'completed_at0',
  firstRecordId: '0',
  lastRecordId: '0',
  monitorId: 'monitor_id6',
  recordCount: BigInt(0),
  requestsFailed: BigInt(0),
  requestsOk: BigInt(0),
  requestsTotal: BigInt(0),
  runId: '0',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

