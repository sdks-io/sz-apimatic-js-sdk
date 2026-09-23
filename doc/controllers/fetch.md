# Fetch

Fetch operations

```ts
const fetchApi = new FetchApi(client);
```

## Class Name

`FetchApi`


# Fetch

```ts
async fetch(
  body: FetchRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FetchResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`FetchRequest`](../../doc/models/fetch-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: One result per requested URL. A failure to fetch a page is still a 200, with that result's `status = "error"`.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FetchResponse`](../../doc/models/fetch-response.md).

## Example Usage

```ts
const body: FetchRequest = {
  urls: [
    'https://example.com/'
  ],
};

try {
  const response = await fetchApi.fetch(body);

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
| 400 | Malformed body, an out-of-bounds or duplicated `urls` entry, or an unavailable `formats` or `tier` value. Unrecognized fields are ignored. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 401 | Invalid or missing API key. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 402 | Insufficient credits. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 429 | Rate limited. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 500 | Unexpected server error. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |

