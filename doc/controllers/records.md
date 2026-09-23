# Records

The delivered records

```ts
const recordsApi = new RecordsApi(client);
```

## Class Name

`RecordsApi`

## Methods

* [List Records](../../doc/controllers/records.md#list-records)
* [List Run Records](../../doc/controllers/records.md#list-run-records)


# List Records

```ts
async listRecords(
  monitorId: string,
  since?: string | null,
  before?: string | null,
  limit?: number | null,
  includeContent?: boolean | null,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListRecordsResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `since` | `string \| null \| undefined` | Query, Optional | Exclusive lower bound on `record_id`. |
| `before` | `string \| null \| undefined` | Query, Optional | Exclusive upper bound on `record_id`. |
| `limit` | `number \| null \| undefined` | Query, Optional | Defaults to 100, at most 1,000. A short page is normal: a page ends at<br>`limit` or at the byte budget, whichever binds first. |
| `includeContent` | `boolean \| null \| undefined` | Query, Optional | Include each record's document content. Defaults to true. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: A page of records.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListRecordsResponse`](../../doc/models/list-records-response.md).

## Example Usage

```ts
const monitorId = 'monitor_id2';

try {
  const response = await recordsApi.listRecords(monitorId);

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
| 404 | No such monitor in this org. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |


# List Run Records

Exists so that no consumer does arithmetic on a record id: a webhook carries a run's record range as a bound, not a dense sequence.

```ts
async listRunRecords(
  monitorId: string,
  runId: string,
  since?: string | null,
  before?: string | null,
  limit?: number | null,
  includeContent?: boolean | null,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListRunRecordsResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `runId` | `string` | Template, Required | - |
| `since` | `string \| null \| undefined` | Query, Optional | Exclusive lower bound on `record_id`. |
| `before` | `string \| null \| undefined` | Query, Optional | Exclusive upper bound on `record_id`. |
| `limit` | `number \| null \| undefined` | Query, Optional | Defaults to 100, at most 1,000. A short page is normal: a page ends at<br>`limit` or at the byte budget, whichever binds first. |
| `includeContent` | `boolean \| null \| undefined` | Query, Optional | Include each record's document content. Defaults to true. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: A page of that run's records.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListRunRecordsResponse`](../../doc/models/list-run-records-response.md).

## Example Usage

```ts
const monitorId = 'monitor_id2';

const runId = 'run_id8';

try {
  const response = await recordsApi.listRunRecords(
    monitorId,
    runId
  );

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
| 404 | No such run on this monitor. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |

