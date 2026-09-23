
# Monitor Status 2

Set to `paused` to create the monitor without starting it. Only `active`
and `paused` are accepted. Defaults to `active`.

## Enumeration

`MonitorStatus2`

## Fields

| Name |
|  --- |
| `Active` |
| `Paused` |
| `Disabled` |
| `Deleted` |

## Example

```ts
import { MonitorStatus2 } from 'sz-apimatic-sdk';

const monitorStatus2 = MonitorStatus2.Active;
```

