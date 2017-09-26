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

| stringwrite_config_bool |
| [Prev](apis.stringwrite_canonical_crlf.php)  | Chapter 51. String Functions |  [Next](apis.stringwrite_config_int.php) |

<a name="apis.stringwrite_config_bool"></a>
## Name

stringwrite_config_bool — Output a boolean to the system console

## Synopsis

`#include "misc/ec_string.h"`

| `string * **stringwrite_config_bool** (` | <var class="pdparam">str</var>, |   |
|   | <var class="pdparam">label</var>, |   |
|   | <var class="pdparam">value</var>, |   |
|   | <var class="pdparam">xml</var>`)`; |   |

`string * <var class="pdparam">str</var>`;
`const char * <var class="pdparam">label</var>`;
`int <var class="pdparam">value</var>`;
`int <var class="pdparam">xml</var>`;<a name="idp35564576"></a>
## Description

Output a boolean to the system console

### Note

This function is deprecated in Momentum version 3.0\. It is suitable only for supporting legacy modules doing 'write config'.

**Parameters**

<dl class="variablelist">

<dt>str</dt>

<dd>

An ec_string.

</dd>

<dt>label</dt>

<dd>

A character array, typically an option name.

</dd>

<dt>int</dt>

<dd>

The value of `label`.

</dd>

<dt>xml</dt>

<dd>

Whether or not to render as XML. Set this value to `0` or `1`.

</dd>

</dl>

**Return Values**

This function returns an ec_string terminated by a newline.

**Threading**

It is legal to call this function in any thread.

| [Prev](apis.stringwrite_canonical_crlf.php)  | [Up](string.php) |  [Next](apis.stringwrite_config_int.php) |
| stringwrite_canonical_crlf  | [Table of Contents](index.php) |  stringwrite_config_int |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)