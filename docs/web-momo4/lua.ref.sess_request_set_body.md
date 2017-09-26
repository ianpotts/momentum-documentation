Logged in as: OmniTI, Inc.  ([logout](https://support.messagesystems.com/logout.php))

[![Message Systems](https://support.messagesystems.com/images/ms-white205.png)](https://support.messagesystems.com/start.php) 

*   [Changelog](https://support.messagesystems.com/start.php?show=changelog)
*   [Documentation](https://support.messagesystems.com/docs/)
*   [Downloads](https://support.messagesystems.com/start.php)

*   [Licenses](https://support.messagesystems.com/license_summary.php)
*   <a href="">Clients</a>
    *   [Support](https://support.messagesystems.com/cs.php)
    *   [Add/Edit](https://support.messagesystems.com/edit_client.php)
    *   [Legal/Products](https://support.messagesystems.com/edit_products.php)
*   [Users](https://support.messagesystems.com/edit_customer.php)

## Search Help

Search for a single word or perform multi-word searches by enclosing your search in quotation marks.

Where you have multiple words but no quotation marks, an **OR** search is performed. For example, **"REST Injection"** searches for the phrase **"REST Injection"**, and, without quotation marks, searches for **REST OR Injection**--the operator is understood.

### Warning

You must escape the following special characters: **+ - && || ! ( ) { } [ ] ^ " ~ * ? : \**. Use the **\** character as the escape character. For example: **B0/00-11719-46C328D4\:default\:**

You can also perform **AND** searches, for example, **rest AND port** (no quotation marks) finds pages where both these words occur.

Terms used in searches are case-insensitive but operators are not. Alphabetic operators **must** be in uppercase.

Other operators can also be used. For more information see "[Query Parser Syntax](https://lucene.apache.org/core/old_versioned_docs/versions/3_0_0/queryparsersyntax.html)". Use of fields in searches is not currently supported.

| sess:request_set_body |
| [Prev](lua.ref.sess_request_finalize.php)  | Chapter 70. Lua Functions Reference |  [Next](lua.ref.msys.httpclnt.http_status_classifier.php) |

<a name="lua.ref.sess_request_set_body"></a>
## Name

sess:request_set_body — Set the body of an HTTP session

<a name="idp15306928"></a>
## Synopsis

`require('msys.httpclnt')`

`sess:request_set_body(request);`

`request: JSON string`<a name="idp15310640"></a>
## Description

Set the body of an HTTP session. `request` is a JSON-formatted string. You must call [sess:request_finalize](lua.ref.sess_request_finalize.php "sess:request_finalize") after invoking this function.

For a code example see [http_request_eval](https://support.messagesystems.com/docs/web-push/push.http_request_eval.php).

<a name="idp15314640"></a>
### See Also

[sess:request_finalize](lua.ref.sess_request_finalize.php "sess:request_finalize") and [sess:request_add_header](lua.ref.sess_request_add_header.php "sess:request_add_header")

| [Prev](lua.ref.sess_request_finalize.php)  | [Up](lua.function.details.php) |  [Next](lua.ref.msys.httpclnt.http_status_classifier.php) |
| sess:request_finalize  | [Table of Contents](index.php) |  msys.httpclnt.http_status_classifier |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)