
# Search Response

*This model accepts additional fields of type unknown.*

## Structure

`SearchResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documents` | [`Document[] \| undefined`](../../doc/models/document.md) | Optional | Documents that are most relevant to the query |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { SearchResponse } from 'stz-apimatic-sdk';

const searchResponse: SearchResponse = {
  documents: [
    {},
    {
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

