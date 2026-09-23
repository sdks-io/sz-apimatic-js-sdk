
# Document

A single search result.

`url` and `published_date` are returned without being asked for, and either
may still be absent for a document that carries no such value. The remaining
members are populated only when `SearchRequest.fields` asked for them.

*This model accepts additional fields of type unknown.*

## Structure

`Document`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `content` | `string \| null \| undefined` | Optional | - |
| `publishedDate` | `string \| null \| undefined` | Optional | Publication date as ISO 8601 string (e.g. "2024-03-15T00:00:00Z") |
| `snippets` | [`Snippet[] \| undefined`](../../doc/models/snippet.md) | Optional | The document's highest-scoring snippets, in the order they appear in the document.<br><br>Populated when `fields.snippets` is selected and passages are available;<br>empty otherwise. |
| `url` | `string \| null \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Document } from 'stz-apimatic-sdk';

const document: Document = {
  content: 'content0',
  publishedDate: 'published_date0',
  snippets: [
    {},
    {
    }
  ],
  url: 'url0',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

