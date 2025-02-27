
# 3.0.2-dev.1 2019.9.20

- fix #470 #471

# 3.0.1 2019.9.20

- Fix #467
- Export `DioForNative` and `DioForBrowser` classes.

# 3.0.0

### New features

- Support Flutter Web.
- Extract [CookieManager](https://github.com/flutterchina/dio/tree/master/plugins/cookie_manager) into a separate package（No need for Flutter Web）.
- Provides a [HTTP/2.0 HttpClientAdapter](https://github.com/flutterchina/dio/tree/master/plugins/http2_adapter).

### Change List

- ~~Options.cookies~~

- ~~Options.connectionTimeout~~ ；We should config connection timed out  in `BaseOptions`.  For keep-alive reasons, not every request requires a separate connection。

- `Options.followRedirects`、`Options.maxRedirects`、`Response.redirects`  don't make sense in Flutter Web，because redirection  can be automatically handled by browsers.

- ~~FormData.from~~，use `FormData.fromMap` instead.

- Delete ~~Formdata.asBytes()~~、~~Formdata.asBytesAsync()~~ , use `Formdata.readAsBytes()` instead.

- Delete ~~`UploadFileInfo`~~ class， `MultipartFile` instead.

- The return type of Interceptor's callback changes from `FutureOr<dynamic>` to `Future`. The reason is [here](https://dart.dev/guides/language/effective-dart/design#avoid-using-futureort-as-a-return-type) .

- The type of `Response.headers` changes from `HttpHeaders` to `Headers`, because `HttpHeaders` is in "dart:io" library which is not supported in Flutter Web.

  




# 2.1.16

Add `deleteOnError` parameter to `downloadUri`

# 2.1.14

- fix #402 #385 #422

# 2.1.13

- fix #369

# 2.1.12

- fix #367 #365

# 2.1.10

- fix #360

# 2.1.9

- support flutter version>=1.8 (fix #357)


# 2.1.8

- fix #354 #312
- Allow "delete" method with request body(#223)

# 2.1.7

- fix #321 #318

# 2.1.6

- fix https://github.com/flutterchina/dio/issues/316

# 2.1.5

- fix https://github.com/flutterchina/dio/issues/309

# 2.1.4

- Add `options.responseDecoder`
- Make DioError catchable by implementing Exception instead of Error

# 2.1.3

Add `statusMessage` attribute for `Response` and `ResponseBody`

# 2.1.2

First Stable version for 2.x

# 2.0

**Refactor the Interceptors**
- Support add Multiple Interceptors.
- Add Log Interceptor
- Add CookieManager Interceptor

**API**
- Support Uri
- Support `queryParameters` for all request API
- Modify the `get` API

**Options**
- Separate Options to three class: Options、BaseOptions、RequestOptions
- Add `queryParameters` and `cookies` for BaseOptions

**Adapter**
- Abstract HttpClientAdapter layer.
- Provide a DefaultHttpClientAdapter which make http requests by `dart:io:HttpClient`

## 0.1.8

- change file name "TransFormer" to "Transformer"
- change "dio.transFormer" to "dio.transformer"
- change deprecated "UTF8" to "utf8"

## 0.1.5

- add `clear` method for dio instance

## 0.1.4

- fix `download` bugs

## 0.1.3

- support upload files with Array
- support create `HttpClient` by user self in `onHttpClientCreate`
- support generic
- bug fix

## 0.0.1

- Initial version, created by Stagehand
