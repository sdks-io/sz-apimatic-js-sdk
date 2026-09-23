
# Create Agent Run Request

## Structure

`CreateAgentRunRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiKey` | `string \| null \| undefined` | Optional | The API key, on gRPC requests. REST reads the `x-api-key` header instead. |
| `effort` | `string \| null \| undefined` | Optional | Effort level: how much research the run may do, and its price. One of<br>the configured level names (e.g. `low`, `medium`, `high`, `max`).<br>Omitted = the default level. |
| `outputSchema` | `unknown \| null \| undefined` | Optional | Optional OpenAI-style `response_format` object requesting structured<br>output: `{"type": "text" \| "json_object" \| "json_schema", ...}`, with<br>`name` / `schema` / `strict` for type `json_schema`. A structured type<br>adds `output.structured` and its `grounding` alongside the cited text;<br>type `text` is accepted and requests no structure. On gRPC the object is<br>JSON-encoded. |
| `query` | `string \| undefined` | Optional | The natural-language question. Instructions inside the query are<br>followed. |

## Example

```ts
import { CreateAgentRunRequest } from 'sz-apimatic-sdk';

const createAgentRunRequest: CreateAgentRunRequest = {
  apiKey: 'api_key6',
  effort: 'effort6',
  outputSchema: { 'key1': 'val1', 'key2': 'val2' },
  query: 'query6',
};
```

