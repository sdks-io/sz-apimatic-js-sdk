# Monitors

Monitor configuration

```ts
const monitorsApi = new MonitorsApi(client);
```

## Class Name

`MonitorsApi`

## Methods

* [List Monitors](../../doc/controllers/monitors.md#list-monitors)
* [Create Monitor](../../doc/controllers/monitors.md#create-monitor)
* [Get Monitor](../../doc/controllers/monitors.md#get-monitor)
* [Delete Monitor](../../doc/controllers/monitors.md#delete-monitor)
* [Update Monitor](../../doc/controllers/monitors.md#update-monitor)


# List Monitors

```ts
async listMonitors(
  name?: string | null,
  status?: string | null,
  since?: string | null,
  before?: string | null,
  limit?: number | null,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListMonitorsResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string \| null \| undefined` | Query, Optional | Matches a monitor whose name is exactly this. |
| `status` | `string \| null \| undefined` | Query, Optional | One of `active`, `paused`, `disabled`. `deleted` is not a filter: a<br>deleted monitor is invisible. |
| `since` | `string \| null \| undefined` | Query, Optional | Exclusive lower bound: the `monitor_id` of a monitor to start after. |
| `before` | `string \| null \| undefined` | Query, Optional | Exclusive upper bound. The list is newest first, so page forward with<br>the `monitor_id` of the last monitor on the previous page. |
| `limit` | `number \| null \| undefined` | Query, Optional | Defaults to 100, at most 1,000. A short page is normal: a page ends at<br>`limit` or at the byte budget, whichever binds first. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: The org's monitors.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListMonitorsResponse`](../../doc/models/list-monitors-response.md).

## Example Usage

```ts
try {
  const response = await monitorsApi.listMonitors();

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


# Create Monitor

```ts
async createMonitor(
  body: CreateMonitorRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CreateMonitorResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateMonitorRequest`](../../doc/models/create-monitor-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**201**: Created. `webhook_secret` is returned once and never again.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CreateMonitorResponse`](../../doc/models/create-monitor-response.md).

## Example Usage

```ts
const body: CreateMonitorRequest = {
  cadence: 'cadence2',
};

try {
  const response = await monitorsApi.createMonitor(body);

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
| 400 | Missing or malformed fields. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 401 | Invalid or missing API key. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 409 | That name is already taken in this org. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |


# Get Monitor

```ts
async getMonitor(
  monitorId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetMonitorResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: The monitor.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetMonitorResponse`](../../doc/models/get-monitor-response.md).

## Example Usage

```ts
const monitorId = 'monitor_id2';

try {
  const response = await monitorsApi.getMonitor(monitorId);

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


# Delete Monitor

```ts
async deleteMonitor(
  monitorId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown | undefined>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Deleted. Every record becomes invisible at once.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const monitorId = 'monitor_id2';

try {
  const response = await monitorsApi.deleteMonitor(monitorId);

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


# Update Monitor

```ts
async updateMonitor(
  monitorId: string,
  body: UpdateMonitorRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UpdateMonitorResponse>>
```

## Authentication

This endpoint requires [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `monitorId` | `string` | Template, Required | - |
| `body` | [`UpdateMonitorRequest`](../../doc/models/update-monitor-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Updated.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UpdateMonitorResponse`](../../doc/models/update-monitor-response.md).

## Example Usage

```ts
const monitorId = 'monitor_id2';

const body: UpdateMonitorRequest = {
  cadence: 'cadence2',
};

try {
  const response = await monitorsApi.updateMonitor(
    monitorId,
    body
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
| 404 | No such monitor in this org. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |
| 409 | That name is already taken in this org. | [`ErrorEnvelopeError`](../../doc/models/error-envelope-error.md) |

