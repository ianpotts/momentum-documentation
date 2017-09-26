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

| msc_thread_id |
| [Prev](apis.if_arp_cache.php)  | Chapter 35. Miscellaneous Functions |  [Next](module.config.php) |

<a name="apis.msc_thread_id"></a>
## Name

msc_thread_id — Generate a thread_id according the following format: [msg_id in spool name format]::[node name]:[suffix]

## Synopsis

`#include "modules/logging/ec_msc_logger.h"`

| `void **msc_thread_id** (` | <var class="pdparam">mid</var>, |   |
|   | <var class="pdparam">suffix</var>, |   |
|   | <var class="pdparam">thread_id</var>, |   |
|   | <var class="pdparam">thread_id_len</var>`)`; |   |

`message_id <var class="pdparam">mid</var>`;
`const char * <var class="pdparam">suffix</var>`;
`char * <var class="pdparam">thread_id</var>`;
`int <var class="pdparam">thread_id_len</var>`;<a name="idp30169840"></a>
## Description

### Note

This reference page was automatically generated from functions found in the header files in the development branch. The function described here may not exist in generally available versions of Momentum, and may change in behavior when it is generally available. Consult your vendor for definitive advice on the use of this function.

Generate a thread_id according the following format: [msg_id in spool name format]::[node name]:[suffix].

[node name] will get its value from cluster configuration if available. In a none-cluster setting, it will use ENV("EC_NODE_NAME") if available otherwise use "default".

**Parameters**

<dl class="variablelist">

<dt>mid</dt>

<dd>

- message id

</dd>

<dt>suffix</dt>

<dd>

- the suffix to be appended to thread_id.

</dd>

<dt>thread_id</dt>

<dd>

- char buffer to hold the generated thread_id.

</dd>

<dt>thread_id_len</dt>

<dd>

- the buffer size of thread_id.

</dd>

</dl>

**Configuration Change. ** This feature is available as of version 3.2.

| [Prev](apis.if_arp_cache.php)  | [Up](misc.php) |  [Next](module.config.php) |
| if_arp_cache  | [Table of Contents](index.php) |  Chapter 36. Module Configuration Functions |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)