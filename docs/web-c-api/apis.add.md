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

| add |
| [Prev](ec_message.php)  | Chapter 34. Message Functions |  [Next](apis.ec_async_fail.php) |

<a name="apis.add"></a>
## Name

add — Add disclaimer to a message

## Synopsis

`#include "modules/generic/disclaimer_api.h"`

| `int **add** (` | <var class="pdparam">mess</var>, |   |
|   | <var class="pdparam">plain_text</var>, |   |
|   | <var class="pdparam">html_text</var>`)`; |   |

`ec_message * <var class="pdparam">mess</var>`;
`const char * <var class="pdparam">plain_text</var>`;
`const char * <var class="pdparam">html_text</var>`;<a name="idp27663952"></a>
## Description

### Note

This reference page was automatically generated from functions found in the header files in the development branch. The function described here may not exist in generally available versions of Momentum, and may change in behavior when it is generally available. Consult your vendor for definitive advice on the use of this function.

Add disclaimer to a message.

If plain_text is not null, all message parts of type text/plain will be appended with plain_text. If html_text is not null, all message parts of type text/html will be appended with html_text.

**Parameters**

<dl class="variablelist">

<dt>mess</dt>

<dd>

- the message

</dd>

<dt>plain_text</dt>

<dd>

- contains plain text version of disclaimer

</dd>

<dt>html_text</dt>

<dd>

- contains html text version of disclaimer

</dd>

</dl>

**Return Values**

0 if disclaimer module is not configured; 1 otherwise.

**Configuration Change. ** This feature is available starting from Momentum 3.1.

| [Prev](ec_message.php)  | [Up](ec_message.php) |  [Next](apis.ec_async_fail.php) |
| Chapter 34. Message Functions  | [Table of Contents](index.php) |  ec_async_fail |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)