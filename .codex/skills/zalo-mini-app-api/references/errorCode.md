# Errors

> Source: https://docs.zaloplatforms.com/docs/MA/api/errorCode
> Last updated: 28/10/2026
> Supported from: SDK 2.21.0

## Error handling guide

Most APIs in the ZMP SDK return a Promise when used, so you can get the returned result and handle errors as follows:

### 1. Use `async/await` together with `try/catch` (recommended)

[async/await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) is a modern JavaScript mechanism supported in most current web environments. Using `async/await` helps handle asynchronous logic linearly and avoids callback hell.

```ts
const { userInfo } = await getUserInfo({
  autoRequestPermission: true,
});
const { orders } = await fetchOrders({
  userId: userInfo.id,
});
console.log("User orders: ", orders);
```

> **Note**
>
> `await` must be called inside an `async` function. For example:
>
> ```
> function login() { // ❌ Cannot use await in a regular function because JavaScript is non-blocking
>
>
>
> await getUserInfo();
>
>
>
> }
>
>
>
> async function login() { // ✅ Valid
>
>
>
> await getUserInfo();
>
>
>
> }
> ```

To handle errors when using `async/await`, you can use `try/catch` as usual:

```ts
try {
    const { userInfo } = await getUserInfo({
        autoRequestPermission: true,
    });
    const { orders } = await fetchOrders({
        userId: userInfo.id,
    });
} catch (error) {
    if (error instanceof AppError) {
        if (error.code === -1401) {
            // The user declined to provide their name and profile picture
        }
        // Another error when calling `getUserInfo`
    } else {
        // Another error when calling `fetchOrders`
    }
}
```

### 2. Use Promise methods such as `.then()` and `.catch()`

You can use this approach if you do not want to switch the current context to `async`. However, if you need to chain many methods, this approach can lead to callback hell:

```ts
getUserInfo({
  autoRequestPermission: true,
}).then(({ userInfo }) => {
  fetchOrders({
    userId: userInfo.id,
  }).then((orders) => {
    console.log("User orders: ", orders);
  });
});
```

To handle errors when using `.then()`, you need to use `.catch()`:

```ts
getUserInfo({
  autoRequestPermission: true,
})
  .then(({ userInfo }) => {
    fetchOrders({
      userId: userInfo.id,
    })
      .then((orders) => {
        console.log("User orders: ", orders);
      })
      .catch((error) => {
        // Error when calling `fetchOrders`
      });
  })
  .catch((error) => {
    if (error instanceof AppError) {
      if (error.code === -1401) {
        // The user declined to provide their name and profile picture
      }
      // Another error when calling `getUserInfo`
    }
  });
```

### 3. Use the ZMP SDK's `success` and `fail` callbacks

All ZMP SDK APIs support passing two special callbacks, `success` and `fail`. The `success` callback is called when the API succeeds and returns the result:

> **Note**
>
> When using these callbacks, the API will **not** return a Promise anymore.

```ts
getUserInfo({
  autoRequestPermission: true,
  success: ({ userInfo }) => {
    fetchOrders({
      userId: userInfo.id,
      success: (orders) => {
        console.log("User orders: ", orders);
      },
    });
  },
});
```

To handle errors, you can pass the `fail` callback similarly:

```ts
getUserInfo({
  autoRequestPermission: true,
  success: ({ userInfo }) => {
    fetchOrders({
      userId: userInfo.id,
      success: (orders) => {
        console.log("User orders: ", orders);
      },
      fail: (error) => {
        // Error when calling `fetchOrders`
      },
    });
  },
  fail: (error) => {
    if (error.code === -1401) {
      // The user declined to provide their name and profile picture
    }
    // Another error when calling `getUserInfo`
  },
});
```

## Error code specification

- Error codes that do not mention **API(s)** apply to **all APIs** in the ZMP SDK.
- Error codes **> 0** are **Server-to-Server** integration errors, such as retrieving a phone number from the token of `getPhoneNumber`.

| Code | Message | Note |
| --- | --- | --- |
| -203 | This action reached the limit | You have exceeded the allowed number of API calls. |
| -1400 | Bad request | The parameters passed to the API are invalid. |
| -1403 | You don | You need to request permission on the App Management page. |
| -1404 | This API is not supported in this version of Zalo | Please [update Zalo](https://docs.zaloplatforms.com/docs/MA/api/zalo/requestUpdateZalo) to use the new APIs. |
| -1408 | Request timeout. Please try again later. | The request took too long to process. Please try again later. |
| -2000 | Unknown error. Please try again later. | An unknown error occurred. Please try again later. |
| -2001 | Can not decode id. Please check your params again. | The ID passed to the API is invalid. |
| 108 | Too many authentication attempts => Biometric authentication locked | You have authenticated too many times; the biometric authentication feature has been locked. |
| 103 | Authentication failed (Chose to enter password - iOS) | Biometric authentication failed; the user chose to enter a password on iOS. |
| 102 | Authentication canceled | The user canceled the authentication process. |
| 101 | Authentication failed 3 times (Android) | The user failed authentication 3 consecutive times on Android. |
| 100 | Unknown error | An unknown error occurred during biometric authentication. |
| -201 | User deny request permission! | The user denied the access permission. |
| -202 | User deny request permission! | The user denied permission and chose not to ask again next time. |
| -2002 | User denied | The user previously denied permission and does not want to be asked again. |
| -1401 | User Authentication Required. Please grant User Authentication permission before requesting User Permission | The user has not provided authentication information. Please refer to [getAccessToken](https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getAccessToken) for more details. |
| 114 | code is empty | The code parameter passed in is empty. |
| 115 | code is invalid | The code parameter passed in is invalid. |
| 116 | secret\_key is empty | The secret\_key parameter passed in is empty. |
| 117 | secret\_key is invalid | The secret\_key parameter passed in is invalid. |
| 118 | code is invalid | The code parameter is invalid; it belongs to another app. |
| 119 | code has already been used | This code has already been used. |
| -301 | Your device run out of storage | Your device has run out of storage space. |
| -302 | File cannot be found. Please check your param again. | File not found. This may be because the path uses http (only https is supported) or the file does not exist. |
| -303 | Please wait... We | The file is being downloaded. Please wait a moment. |
| -304 | No Internet connection. Please check your network settings. | No Internet connection. Please check your network. |
| -305 | Download failed. Please check your network or file path again. | File download failed. Please check your network connection or the file path. |
| -306 | File type unsupported | The file format is not supported. See the [list of supported files](https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile#support-file-type). |
| -2003 | User cancel | The user canceled the media selection. |
| -2004 | Unable to pick media | Unable to select media. Please check your network connection or the upload server. |
| -2005 | Unable to save image | Unable to save media to the photo library. |
| -2006 | Unable to save video | Unable to save the video to the library. |
| -700 | Download failed. Please check your URL again. | The URL is invalid. |
| -701 | Unsupported file type | The file format is not supported. |
| -702 | Download failed. Please check your network or file path again. | File download failed. |
| -703 | Open document failed | Failed to open the document. |
