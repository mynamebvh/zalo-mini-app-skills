# getContextAsync

> Source: https://docs.zaloplatforms.com/docs/MA/api/basics/getContextAsync
> Last updated: 28/10/2026
> Supported from: SDK 2.22.0, Android 22.06.02

```ts
import { getContextAsync } from "zmp-sdk";
```

API that returns the context information of the user or group when the Mini App is opened from the extended Menu in the Zalo chat window.
If the context is invalid or the Zalo version does not support it, the returned value will be empty.

## Example

Check whether the context is valid and return the context information:

```ts
const contextInfo = await getContextAsync();
if (contextInfo) {
  // Valid context
  const { id, type } = contextInfo;
}
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Promise<ContextInfo>` containing the current context.

### ContextInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `'USER_CHAT' \| 'GROUP_CHAT' \| ''` | No | The current context is a user or a group chat. |
| id | `string` | No | ID of the corresponding user or group chat. |