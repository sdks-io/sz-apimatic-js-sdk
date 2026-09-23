
# Fields 2

Which selectable members of `Document` to populate.

If absent, defaults to `{content: true}`, which returns content under the
default ceiling stated on `ContentOptions`.

*This model accepts additional fields of type unknown.*

## Structure

`Fields2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `content` | [`Fields2Content \| undefined`](../../doc/models/containers/fields-2-content.md) | Optional | This is a container for one-of cases. |
| `snippets` | [`Fields2Snippets \| undefined`](../../doc/models/containers/fields-2-snippets.md) | Optional | This is a container for one-of cases. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Fields2 } from 'stz-apimatic-sdk';

const fields2: Fields2 = {
  content: true,
  snippets: true,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

