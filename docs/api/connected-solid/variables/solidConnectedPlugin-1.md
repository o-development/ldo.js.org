# Variable: solidConnectedPlugin

• `Const` **solidConnectedPlugin**: [`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)

This plugin can be given to a ConnectedDataset to let it connect to Solid
servers.

**`Example`**

```
import { createConnectedLdoDataset } from "@ldo/connected";
import { solidConnectedPlugin } from "@ldo/connected-solid";

const solidConnectedDataset = createConnectedLdoDataset([
  solidConnectedPlugin
]);
```

#### Defined in

[packages/connected-solid/src/SolidConnectedPlugin.ts:64](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/SolidConnectedPlugin.ts#L64)
