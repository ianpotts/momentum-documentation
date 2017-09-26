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

| msys.idn.to_idn |
| [Prev](lua.ref.msys.getClassMetaTable.php)  | 15.2. Lua Functions |  [Next](lua.ref.msys.idn_utf8.php) |

<a name="lua.ref.msys.idn"></a>
## Name

msys.idn.to_idn — Attempts to convert the domain to the IDN format

<a name="idp24501344"></a>
## Synopsis

`msys.idn.to_idn(name);`

`name: string`<a name="idp24503632"></a>
## Description

**Configuration Change. ** This feature is available as beta in Momentum 3.6.12.

to_idn() assumes its argument to be a utf-8 formatted domain name. It attempts to convert the domain to the IDN format. If it is successful, it returns the ASCII version of the resulting IDN string (Note: the underlying encoding is unicode, but the characters are ASCII). If it fails, an error is returned.

<a name="msys.idn.to_idn.example"></a>

**Example 15.30. msys.idn example**

```
local newMsg = msys.core.ec_message_new(nil)
local headers = {}
local parts = {}

parts['text/plain'] = "this is a sample message"
headers['from'] = [[From: “John Doe =?utf-8?Q?=28?=" <弗兰克@example.com>]]
newMsg:build(headers, parts, {})

local domains = newMsg:address_header("From", "domain");
local idn = msys.idn.to_idn(domains[1]);
local utf8 = msys.idn.to_utf8(idn);
print ("Original: " .. domains[1] .. " IDN: " .. idn .. " UTF8: " .. utf8);
```

This function wil help facilitate the translation of international characters to and from unicode in order to support internationalized domain names and international email.

<a name="idp24510480"></a>
## See Also

[msys.idn.to_utf8](lua.ref.msys.idn_utf8.php "msys.idn.to_utf8")

| [Prev](lua.ref.msys.getClassMetaTable.php)  | [Up](lua.function.details.php) |  [Next](lua.ref.msys.idn_utf8.php) |
| msys.getClassMetaTable  | [Table of Contents](index.php) |  msys.idn.to_utf8 |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)