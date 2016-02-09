<p align="center">
  x
</p>
<p align="center">
  <i>x</i>
</p>

&nbsp;

# Akaria
雅卡莉亞（Akaria）是用來回傳 HTTP 狀態碼的 PHP 函式庫，簡化了 `header()` 的必要。

&nbsp;

# 特色

1. 免去 `header()` 的困擾。

2. 簡短了驗證 HTTP 狀態碼的方式。

&nbsp;

## 教學

雅卡莉亞不需要被初始化，因此你可以直接依照下列程式碼開始使用雅卡莉亞。

&nbsp;

### 回傳

你可以直接透過下列方式回傳一個 404 代碼。

```php
Akaria::say(404);

/** 或者 */
Akaria::say('NOT_FOUND');
```

&nbsp;

### 正面或負面

你也可以直接透過 `positive()` 和 `negative()` 來確認這個狀態碼是好還是壞。

例如 `404` 是 `False`，而 `200` 則會回傳 `True`。

```php
Akaria::positive(404);   // False
Akaria::negative(404);   // True
Akaria::positive(200);   // True
Akaria::positive(500);   // False
```

&nbsp;

### 驗證狀態碼

透過 `is()` 來在數字和狀態碼之間做確認的動作。

```php
Akaria::is(404, 'NOT_FOUND');   // True
Akaria::is(200, 'CREATED');     // False
```

&nbsp;

## 對照表和縮寫

| 狀態碼 | 正常縮寫                             | 雅卡莉亞縮寫            | 正面 |
|--------|--------------------------------------|-------------------------|------|
| 100    | Continue                             | CONTINUE                | ✓    |
| 101    | Switching Protocols                  | SWITCHING               | ✓    |
| 102    | Processing                           | PROCESSING              | ✓    |
| 200    | OK                                   | OK                      | ✓    |
| 201    | Created                              | CREATED                 | ✓    |
| 202    | Accepted                             | ACCEPTED                | ✓    |
| 203    | Non-Authoritative Information        | NON_AUTH                | ✓    |
| 204    | No Content                           | NO_CONTENT              | ✓    |
| 205    | Reset Content                        | RESET_CONTENT           | ✓    |
| 206    | Partial Content                      | PARTIAL_CONTENT         | ✓    |
| 207    | Multi-Status                         | MULTI_STATUS            | ✓    |
| 208    | Already Reported                     | ALREADY_REPORTED        | ✓    |
| 226    | IM Used                              | IM_USED                 | ✓    |
| 300    | Multiple Choices                     | CHOICES                 | ✓    |
| 301    | Moved Permanently                    | MOVED                   | ✓    |
| 302    | Found                                | FOUND                   | ✓    |
| 303    | See Other                            | OTHER                   | ✓    |
| 304    | Not Modified                         | NOT_MODIFIED            | ✓    |
| 305    | Use Proxy                            | PROXY                   | ✓    |
| 306    |                                      |                         |      |
| 307    | Temporary Redirect                   | TEMP_REDIRECT           | ✓    |
| 308    | Permanent Redirect                   | PERM_REDIRECT           | ✓    |
| 400    | Bad Request                          | BAD                     |      |
| 401    | Unauthorized                         | UNAUTHORIZED            |      |
| 402    | Payment Required                     | PAYMENT_REQUIED         |      |
| 403    | Forbidden                            | FORBIDDEN               |      |
| 404    | Not Found                            | NOT_FOUND               |      |
| 405    | Method Not Allowed                   | METHOD_NOT_ALLOWED      |      |
| 406    | Not Acceptable                       | NOT_ACCEPTABLE          |      |
| 407    | Proxy Authentication Required        | PROXY_AUTH_REQUIRED     |      |
| 408    | Request Timeout                      | REQUEST_TIMEOUT         |      |
| 409    | Conflict                             | CONFLICT                |      |
| 410    | Gone                                 | GONE                    |      |
| 411    | Length Required                      | LENGTH_REQUIRED         |      |
| 412    | Precondition Failed                  | PRECONDITION_FAILED     |      |
| 413    | Request Entity Too Large             | ENTITY_TOO_LARGE        |      |
| 414    | Request-URI Too Long                 | URL_TOO_LONG            |      |
| 415    | Unsupported Media Type               | UNSUPPORTED             |      |
| 416    | Requested Range Not Satisfiable      | REQUESTED_RANGE         |      |
| 417    | Expectation Failed                   | EXPECTATION_FAILED      |      |
| 418    | I'm a teapot                         | TEAPOT                  |      |
| 420    | Enhance Your Calm                    | ENHANCE                 |      |
| 422    | Unprocessable Entity                 | UNPROCESSABLE           |      |
| 423    | Locked                               | LOCKED                  |      |
| 424    | Failed Dependency                    | FAILED_DEPENDENCY       |      |
| 425    | Reserved for WebDAV                  | RESERVED                |      |
| 426    | Upgrade Required                     | UPGRADE_REQUIRED        |      |
| 428    | Precondition Required                | PRECONDITION_REQUIRED   |      |
| 429    | Too Many Requests                    | TOO_MANY                |      |
| 431    | Request Header Fields Too Large      | FIELDS_TOO_LARGE        |      |
| 444    | No Response                          | NO_RESPONSE             |      |
| 449    | Retry With                           | RETRY_WITH              |      |
| 450    | Blocked by Windows Parental Controls | BLOCKED_WPC             |      |
| 499    | Client Closed Request                | CLIENT_CLOSED           |      |
| 500    | Internal Server Error                | ERROR                   |      |
| 501    | Not Implemented                      | NOT_IMPLEMENTED         |      |
| 502    | Bad Gateway                          | BAD                     |      |
| 503    | Service Unavailable                  | UNAVALIABLE             |      |
| 504    | Gateway Timeout                      | GATEWAY_TIMEOUT         |      |
| 505    | HTTP Version Not Supported           | HTTP_NOT_SUPPORTED      |      |
| 506    | Variant Also Negotiates              | VAN                     |      |
| 507    | Insufficient Storage                 | INSUFFICIENT_STORAGE    |      |
| 508    | Loop Detected                        | LOOP                    |      |
| 509    | Bandwidth Limit Exceeded             | BANDWIDTH               |      |
| 510    | Not Extended                         | NOT_EXTENDED            |      |
| 511    | Network Authentication Required      | NETWORK_AUTH_REQUIRED   |      |
| 598    | Network read timeout error           | NETWORK_READ_TIMEOUT    |      |
| 599    | Network connect timeout error        | NETWORK_CONNECT_TIMEOUT |      |

&nbsp;

## 可參考文件

[Hypertext Transfer Protocol (HTTP) Status Code Registry](http://www.iana.org/assignments/http-status-codes)

[symfony@http-foundation](https://github.com/symfony/http-foundation/blob/master/Response.php)

[shrikeh@teapot](https://github.com/shrikeh/teapot)
