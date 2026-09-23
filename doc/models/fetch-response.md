
# Fetch Response

One result per requested URL.

*This model accepts additional fields of type unknown.*

## Structure

`FetchResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `results` | [`FetchResult[] \| undefined`](../../doc/models/fetch-result.md) | Optional | One entry per entry in `FetchRequest.urls`, successful or not, in the order<br>the URLs were requested.<br><br>Correlate on `FetchResult.requested_url` rather than on position. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { FetchResponse } from 'stz-apimatic-sdk';

const fetchResponse: FetchResponse = {
  results: [
    {},
    {
      status: null,
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

