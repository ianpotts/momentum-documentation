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

| spool_disk_queue_state |
| [Prev](apis.mid_to_spool_name.xml.php)  | Chapter 49. Spool-related Functions |  [Next](apis.spool_in.php) |

<a name="apis.spool_disk_queue_state"></a>
## Name

spool_disk_queue_state — Show the state of the queue on disk

## Synopsis

`#include "spool.h"`

| `void **spool_disk_queue_state** (` | <var class="pdparam">total</var>, |   |
|   | <var class="pdparam">progress</var>`)`; |   |

`int * <var class="pdparam">total</var>`;
`int * <var class="pdparam">progress</var>`;<a name="idp35153488"></a>
## Description

Show the state of the queue on disk.

**Parameters**

<dl class="variablelist">

<dt>total</dt>

<dd>

The size of the disk queue.

</dd>

<dt>progress</dt>

<dd>

How much of the queue has been processed.

</dd>

</dl>

**Return Values**

This function returns void. After execution, `total` contains the disk queue size and `progress` shows how much of the queue has been processed.

**Threading**

It is legal to call this function in the `Scheduler` thread.

<a name="idp35163072"></a>
## See Also

| [Prev](apis.mid_to_spool_name.xml.php)  | [Up](spool.php) |  [Next](apis.spool_in.php) |
| mid_to_spool_name  | [Table of Contents](index.php) |  spool_in |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)