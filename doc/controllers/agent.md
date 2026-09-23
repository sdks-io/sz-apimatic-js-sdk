# Agent

Agent runs: create, poll, list, cancel

```ts
const agentApi = new AgentApi(client);
```

## Class Name

`AgentApi`

## Methods

* [List Agent Runs](../../doc/controllers/agent.md#list-agent-runs)
* [Create Agent Run](../../doc/controllers/agent.md#create-agent-run)
* [Get Agent Run](../../doc/controllers/agent.md#get-agent-run)
* [Cancel Agent Run](../../doc/controllers/agent.md#cancel-agent-run)


# List Agent Runs

The organization's runs, newest first. Pass one page's `next` as the following request's `after`.

```ts
async listAgentRuns(
  limit?: bigint,
  after?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListAgentRunsResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `limit` | `bigint \| undefined` | Query, Optional | Page size, 1-100. Defaults to 20. |
| `after` | `string \| undefined` | Query, Optional | Pagination cursor: the previous page's `next`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: One page of runs, newest first.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListAgentRunsResponse`](../../doc/models/list-agent-runs-response.md).

## Example Usage

```ts
try {
  const response = await agentApi.listAgentRuns();

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
| 400 | Malformed or unknown query parameter. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 401 | Invalid or missing API key. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 404 | Unknown `after` cursor. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 500 | Unexpected server error. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |


# Create Agent Run

Returns the new run in `pending` state. Poll it by id until `status` reaches a terminal state.

```ts
async createAgentRun(
  body: CreateAgentRunRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AgentRun>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateAgentRunRequest`](../../doc/models/create-agent-run-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**201**: The new run, in `pending` state.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AgentRun`](../../doc/models/agent-run.md).

## Example Usage

```ts
const body: CreateAgentRunRequest = {
};

try {
  const response = await agentApi.createAgentRun(body);

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
| 400 | Malformed body, unknown field, unknown `effort`, or a rejected `output_schema`. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 401 | Invalid or missing API key. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 402 | Insufficient credits. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 500 | Unexpected server error. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |


# Get Agent Run

Poll until `status` reaches a terminal state.

```ts
async getAgentRun(
  id: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AgentRun>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The run id. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: The run.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AgentRun`](../../doc/models/agent-run.md).

## Example Usage

```ts
const id = 'id0';

try {
  const response = await agentApi.getAgentRun(id);

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
| 401 | Invalid or missing API key. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 404 | No such run in this org. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 500 | Unexpected server error. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |


# Cancel Agent Run

Stop a run that has not finished. Returns the run, unchanged if it had already ended, so cancelling is safe to retry.

```ts
async cancelAgentRun(
  id: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AgentRun>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The run id. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: The run.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AgentRun`](../../doc/models/agent-run.md).

## Example Usage

```ts
const id = 'id0';

try {
  const response = await agentApi.cancelAgentRun(id);

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
| 401 | Invalid or missing API key. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 404 | No such run in this org. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 500 | Unexpected server error. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |

