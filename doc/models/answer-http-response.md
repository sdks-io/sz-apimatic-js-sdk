
# Answer Http Response

Buffered JSON response body for `POST /v1/answer`.

*This model accepts additional fields of type unknown.*

## Structure

`AnswerHttpResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `answer` | `string` | Required | Markdown answer text. Inline citations follow the form<br>`text ([Source Name](url))`. |
| `citations` | [`HttpCitation[]`](../../doc/models/http-citation.md) | Required | The sources the answer was grounded in. Every source the answer was<br>given is returned, whether or not the text cites it. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AnswerHttpResponse } from 'stz-apimatic-sdk';

const answerHttpResponse: AnswerHttpResponse = {
  answer: 'answer4',
  citations: [
    {
      url: 'url2',
      content: 'content2',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

