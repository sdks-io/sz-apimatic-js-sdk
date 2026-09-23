
# Http Citation

HTTP-shape citation. Mirrors the `Citation` proto.

*This model accepts additional fields of type unknown.*

## Structure

`HttpCitation`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `content` | `string \| null \| undefined` | Optional | Document content text (only when `include_content = true`). |
| `url` | `string` | Required | URL of the source document. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { HttpCitation } from 'sz-apimatic-sdk';

const httpCitation: HttpCitation = {
  url: 'url6',
  content: 'content6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

