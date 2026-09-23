
# Answer Http Request

JSON request body for `POST /v1/answer`.

*This model accepts additional fields of type unknown.*

## Structure

`AnswerHttpRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiKey` | `string \| null \| undefined` | Optional | API key. Either this or the `x-api-key` header must be supplied;<br>the header takes precedence. |
| `includeContent` | `boolean \| undefined` | Optional | When true, citations carry the document content text. Default false. |
| `model` | `string \| null \| undefined` | Optional | Selects the answer tier, which determines behavior and billing.<br>Omitted resolves to the default tier. Independent of `scope`; the<br>response shape is unchanged. |
| `query` | `string` | Required | The natural-language question. |
| `responseFormat` | `unknown \| undefined` | Optional | Optional `OpenAI` `response_format` object (`{"type": "text" \| "json_object" \| "json_schema", ...}`), accepted as raw JSON exactly<br>like `/v1/chat/completions`. Under a structured type no inline<br>citations are added, so the answer stays schema-valid; a malformed<br>value is a `400` before billing. Omitted leaves the answer as Markdown<br>prose.<br>Applies at every tier. |
| `scope` | `string \| null \| undefined` | Optional | Restricts the grounding search to one scope.<br><br>Currently available:<br><br>- `news`<br>- `wikipedia`<br>- `people`<br>- `companies`<br><br>Omitted, empty or whitespace-only searches the default scope. |
| `stream` | `boolean \| undefined` | Optional | When true, stream the answer as OpenAI-mimic SSE chunks. Default false. |
| `systemPrompt` | `string \| null \| undefined` | Optional | Steers how the answer is presented — tone, voice, format. It is<br>subordinate to the grounding and citation rules, which stay in force.<br>That precedence is instructional, not a sandbox. Omitted, empty or<br>whitespace-only leaves the presentation unchanged. Applies at every<br>tier and composes with `response_format`. At most 8 KiB of UTF-8; a<br>longer value is a `400` before billing. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AnswerHttpRequest } from 'sz-apimatic-sdk';

const answerHttpRequest: AnswerHttpRequest = {
  query: 'query0',
  apiKey: 'api_key2',
  includeContent: false,
  model: 'model8',
  responseFormat: { 'key1': 'val1', 'key2': 'val2' },
  scope: 'scope2',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

