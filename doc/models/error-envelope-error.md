
# Error Envelope Error

The response body returned for any error.

*This model accepts additional fields of type unknown.*

## Structure

`ErrorEnvelopeError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`EnvelopeError1`](../../doc/models/envelope-error-1.md) | Required | The error context. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof ErrorEnvelopeError) {
    console.log(error.result);
  }
}
```

