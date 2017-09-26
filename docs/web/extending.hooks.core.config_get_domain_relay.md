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

| config_get_domain_relay |
| [Prev](extending.hooks.core.check_outbound_mess_throttle.php)  | Chapter 18. Hooks in the core scope |  [Next](extending.hooks.core.config_get_domain_routes_data_copy.php) |

<a name="extending.hooks.core.config_get_domain_relay"></a>
## Name

config_get_domain_relay

## Synopsis

`#include "hooks/core/config_get_domain_relay.h"`

| `int **config_get_domain_relay**(` | <var class="pdparam">closure</var>, |   |
|   | <var class="pdparam">cs</var>, |   |
|   | <var class="pdparam">domain</var>, |   |
|   | <var class="pdparam">retval</var>`)`; |   |

`void * <var class="pdparam">closure</var>`;
`generic_module_infrastructure * <var class="pdparam">cs</var>`;
`const char * <var class="pdparam">domain</var>`;
`int * <var class="pdparam">retval</var>`;

| `int **has_core_config_get_domain_relay_hook**(` | `)`; |   |

| `void **register_core_config_get_domain_relay_hook_first**(` | <var class="pdparam">hook</var>, |   |
|   | <var class="pdparam">closure</var>`)`; |   |

`ec_hook_core_config_get_domain_relay_func_t <var class="pdparam">hook</var>`;
`void *<var class="pdparam">closure</var>`;

| `void **register_core_config_get_domain_relay_hook_last**(` | <var class="pdparam">hook</var>, |   |
|   | <var class="pdparam">closure</var>`)`; |   |

`ec_hook_core_config_get_domain_relay_func_t <var class="pdparam">hook</var>`;
`void *<var class="pdparam">closure</var>`;

| `int **call_core_config_get_domain_relay_hook**(` | <var class="pdparam">cs</var>, |   |
|   | <var class="pdparam">domain</var>, |   |
|   | <var class="pdparam">retval</var>`)`; |   |

`generic_module_infrastructure * <var class="pdparam">cs</var>`;
`const char * <var class="pdparam">domain</var>`;
`int * <var class="pdparam">retval</var>`;<a name="idp20585520"></a>
## Description

This hook is called to determine whether a given domain should be relayed for. The default action is to check the relay_hosts list, but it can be overridden by registering a custom function at this hook. If the hook returns non-zero, then the value of retval will be set to the relay status for the domain.

| [Prev](extending.hooks.core.check_outbound_mess_throttle.php)  | [Up](extending.hooks.core.php) |  [Next](extending.hooks.core.config_get_domain_routes_data_copy.php) |
| check_outbound_mess_throttle  | [Table of Contents](index.php) |  config_get_domain_routes_data_copy |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)