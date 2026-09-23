
# Getting Started with Seltz API

## Introduction

REST API for the Seltz platform: context retrieval (`/v1/search`), RAG answers (`/v1/answer`), monitors (`/v1/monitors`), and page fetching (`/v1/fetch`).

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install stz-apimatic-sdk@0.0.2
```

For additional package details, see the [Npm page for the stz-apimatic-sdk@0.0.2 npm](https://www.npmjs.com/package/stz-apimatic-sdk/v/0.0.2).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| timeout | `number` | Timeout for API calls.<br>*Default*: `30000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/partial-logging-options.md) | Logging Configuration to enable logging |
| customHeaderAuthenticationCredentials | [`CustomHeaderAuthenticationCredentials`](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/auth/custom-header-signature.md) | The credential object for customHeaderAuthentication |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client, LogLevel } from 'stz-apimatic-sdk';

const client = new Client({
  customHeaderAuthenticationCredentials: {
    'x-api-key': 'x-api-key'
  },
  timeout: 30000,
  logging: {
    logLevel: LogLevel.Info,
    logRequest: {
      logBody: true
    },
    logResponse: {
      logHeaders: true
    }
  },
});
```

### Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'stz-apimatic-sdk';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/configuration-based-client-initialization.md) section for details.

### Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'stz-apimatic-sdk';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/environment-based-client-initialization.md) section for details.

## Authorization

This API uses the following authentication schemes.

* [`ApiKeyAuth (Custom Header Signature)`](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/auth/custom-header-signature.md)

## List of APIs

* [Search](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/controllers/search.md)
* [Answer](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/controllers/answer.md)
* [Monitors](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/controllers/monitors.md)
* [Records](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/controllers/records.md)
* [Runs](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/controllers/runs.md)
* [Agent](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/controllers/agent.md)
* [Fetch](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/controllers/fetch.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/environment-based-client-initialization.md)
* [PartialLoggingOptions](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/partial-logging-options.md)
* [PartialRequestLoggingOptions](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/partial-request-logging-options.md)
* [PartialResponseLoggingOptions](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/partial-response-logging-options.md)
* [LoggerInterface](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/logger-interface.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/api-response.md)
* [ApiError](https://www.github.com/sdks-io/sz-apimatic-js-sdk/tree/0.0.2/doc/api-error.md)

