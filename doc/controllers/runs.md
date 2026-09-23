# Runs

Run history and per-request outcomes

```ts
const runsApi = new RunsApi(client);
```

## Class Name

`RunsApi`

## Methods

* [List Runs](../../doc/controllers/runs.md#list-runs)
* [Get Run](../../doc/controllers/runs.md#get-run)
* [List Run Requests](../../doc/controllers/runs.md#list-run-requests)


# List Runs

```ts
async listRuns(
  monitorId: string,
  since?: string | null,
  before?: string | null,
  limit?: number | null,
  sort?: string | null,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListRunsResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `since` | `string \| null \| undefined` | Query, Optional | Exclusive lower bound on `run_id`. |
| `before` | `string \| null \| undefined` | Query, Optional | Exclusive upper bound on `run_id`. |
| `limit` | `number \| null \| undefined` | Query, Optional | Defaults to 100, at most 1,000. |
| `sort` | `string \| null \| undefined` | Query, Optional | `desc` (the default, newest first) or `asc`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: A page of runs.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListRunsResponse`](../../doc/models/list-runs-response.md).

## Example Usage

```ts
const monitorId = 'monitor_id2';

try {
  const response = await runsApi.listRuns(monitorId);

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


# Get Run

```ts
async getRun(
  monitorId: string,
  runId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetRunResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `runId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: The run. Carries no records and no breakdown.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetRunResponse`](../../doc/models/get-run-response.md).

## Example Usage

```ts
const monitorId = 'monitor_id2';

const runId = 'run_id8';

try {
  const response = await runsApi.getRun(
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


# List Run Requests

The only place a customer can tell *this query failed* from *there was genuinely nothing new*: records are a stream of positives, and absence cannot be inferred from presences.

```ts
async listRunRequests(
  monitorId: string,
  runId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListRunRequestsResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `runId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: That run's per-request outcomes.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListRunRequestsResponse`](../../doc/models/list-run-requests-response.md).

## Example Usage

```ts
const monitorId = 'monitor_id2';

const runId = 'run_id8';

try {
  const response = await runsApi.listRunRequests(
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

