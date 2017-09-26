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

| vctx:set |
| [Prev](lua.ref.vctx_remove_recipient.php)  | 15.2. Lua Functions |  [Next](lua.ref.vctx_set_code.php) |

<a name="lua.ref.vctx_set"></a>
## Name

vctx:set — Set the value of a context variable

<a name="idp27929968"></a>
## Synopsis

`vctx:set(type, key, value);`

```
type: numeric
key: string
value: mixed
```
<a name="idp27932688"></a>
## Description

Set the value of a context variable. The `type` parameter can be either `msys.core.VCTX_MESS` or `msys.core.VCTX_CONN`.

<a name="lua.ref.vctx_set.example"></a>

**Example 15.73. vctx:set example**

```
require("msys.core");
require("msys.brightmail");

local mod = {};
function mod:validate_data(msg, accept, vctx)
  local verdict, is_default, rules, tracker = msys.brightmail.scan(msg, accept, vctx)
    print("verdict:", verdict, " is_default:", is_default, " rules:", rules, " tracker:", tracker)
    vctx:set(msys.core.VCTX_MESS, 'bm_verdict', verdict)
  return msys.core.VALIDATE_CONT;
end
msys.registerModule("bm", mod);
```

Because this function is in the `msys.core` namespace, an explicit `require('msys.core')` is not necessary.

<a name="idp27939712"></a>
## See Also

[vctx:get](lua.ref.vctx_get.php "vctx:get")

| [Prev](lua.ref.vctx_remove_recipient.php)  | [Up](lua.function.details.php) |  [Next](lua.ref.vctx_set_code.php) |
| vctx:remove_recipient  | [Table of Contents](index.php) |  vctx:set_code |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)