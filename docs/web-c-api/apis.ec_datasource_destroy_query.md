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

| ec_datasource_destroy_query |
| [Prev](apis.ec_datasource_cache_query.php)  | Chapter 16. Datasource Functions |  [Next](apis.ec_datasource_first_column.php) |

<a name="apis.ec_datasource_destroy_query"></a>
## Name

ec_datasource_destroy_query — Release the resources used by the specified query

## Synopsis

`#include "modules/datasource/ecdatasource.h"`

| `void **ec_datasource_destroy_query** (` | <var class="pdparam">q</var>`)`; |   |

`ecdata_cache_query * <var class="pdparam">q</var>`;<a name="idp22171952"></a>
## Description

Release the resources used by the specified query.

**Parameters**

<dl class="variablelist">

<dt>q</dt>

<dd>

A pointer to an ecdata_cache_query. The following typedef applies to this data type: `typedef struct ec_datasource_cache_query ecdata_cache_query;`.

</dd>

</dl>

**Return Values**

This function returns void.

**Threading**

It is legal to call this function in any thread.

<a name="idp22178816"></a>
## See Also

[ds_core Module](https://support.messagesystems.com/docs/web-ref/modules.ds_core.php) and [Section 68.25, “ec_datasource_cache_query”](structs.ec_datasource_cache_query.php "68.25. ec_datasource_cache_query")

| [Prev](apis.ec_datasource_cache_query.php)  | [Up](datasource.php) |  [Next](apis.ec_datasource_first_column.php) |
| ec_datasource_cache_query  | [Table of Contents](index.php) |  ec_datasource_first_column |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)