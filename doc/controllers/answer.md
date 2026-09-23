# Answer

Answer operations

```ts
const answerApi = new AnswerApi(client);
```

## Class Name

`AnswerApi`


# Answer

```ts
async answer(
  body: AnswerHttpRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AnswerHttpResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AnswerHttpRequest`](../../doc/models/answer-http-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Answer for the query. When `stream = false` the body is a JSON `AnswerHttpResponse`; when `stream = true` it is a `text/event-stream` of OpenAI-style chunks.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AnswerHttpResponse`](../../doc/models/answer-http-response.md).

## Example Usage

```ts
const body: AnswerHttpRequest = {
  query: 'Who is reported to be Apple\'s next CEO?',
};

try {
  const response = await answerApi.answer(body);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
    if (error instanceof ErrorEnvelopeError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Missing or malformed request fields. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 401 | Invalid or missing API key. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 402 | Insufficient credits. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 404 | Endpoint not found, or a scope that matches nothing. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 405 | Wrong method for this endpoint. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 408 | The answer did not complete in time. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 413 | Request body is too large. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 415 | `Content-Type` is not `application/json`. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 429 | Rate limit exceeded. Wait before retrying. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 500 | Unexpected server error. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |

