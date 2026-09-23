
# Get Run Response

*This model accepts additional fields of type unknown.*

## Structure

`GetRunResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `run` | [`Run \| null \| undefined`](../../doc/models/run.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetRunResponse } from 'stz-apimatic-sdk';

const getRunResponse: GetRunResponse = {
  run: null,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

