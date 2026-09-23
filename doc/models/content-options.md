
# Content Options

The ceiling on the content returned.

The ceiling is an upper bound; the response carries at most what is specified here.

The service may hold callers to a tighter bound than the range below. A larger
request is then served at that bound rather than refused, which still carries at
most what was specified. Only a value outside the range below is rejected.

*This model accepts additional fields of type unknown.*

## Structure

`ContentOptions`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `maxCharactersPerResult` | `number \| null \| undefined` | Optional | Ceiling on the characters of any single result's content.<br><br>Counts Unicode code points -- Rust `char`, Python `len(s)`, JavaScript `\[...s\].length`.<br><br>Defaults to 20000, accepted range 100-1000000.<br><br>**Constraints**: `>= 100`, `<= 1000000` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ContentOptions } from 'sz-apimatic-sdk';

const contentOptions: ContentOptions = {
  maxCharactersPerResult: 192,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

