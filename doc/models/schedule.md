
# Schedule

*This model accepts additional fields of type unknown.*

## Structure

`Schedule`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cadence` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Schedule } from 'sz-apimatic-sdk';

const schedule: Schedule = {
  cadence: 'cadence8',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

