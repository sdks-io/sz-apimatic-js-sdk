
# Search Request Ref

*This model accepts additional fields of type unknown.*

## Structure

`SearchRequestRef`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `query` | `string \| undefined` | Optional | The request's query text, carried here so a record can be rendered without<br>a second lookup. |
| `requestId` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { SearchRequestRef } from 'stz-apimatic-sdk';

const searchRequestRef: SearchRequestRef = {
  query: 'query0',
  requestId: 'request_id8',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

