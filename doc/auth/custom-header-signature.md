
# Custom Header Signature



Documentation for accessing and setting credentials for ApiKeyAuth.

## Auth Credentials

| Name | Type | Description | Setter |
|  --- | --- | --- | --- |
| x-api-key | `string` | Seltz API key. Create one in the [Seltz Console](https://console.seltz.ai/api-keys) under **Settings → API Keys**. | `xApiKey` |



**Note:** Auth credentials can be set using `customHeaderAuthenticationCredentials` object in the client.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```ts
import { Client } from 'sz-apimatic-sdk';

const client = new Client({
  customHeaderAuthenticationCredentials: {
    'x-api-key': 'x-api-key'
  },
});
```


