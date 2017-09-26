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

| generate_soft_bounce_message |
| [Prev](hooks.core.generate_rfc3464_message_preamble.php)  | Chapter 60. Hooks in the core scope |  [Next](hooks.core.generate_soft_bounce_message_preamble.php) |

<a name="hooks.core.generate_soft_bounce_message"></a>
## Name

generate_soft_bounce_message

## Synopsis

`#include "hooks/core/generate_soft_bounce_message.h"`

| `email_message* **generate_soft_bounce_message** (` | <var class="pdparam">closure</var>, |   |
|   | <var class="pdparam">message</var>`)`; |   |

`void * <var class="pdparam">closure</var>`;
`email_message * <var class="pdparam">message</var>`;

| `int **has_core_generate_soft_bounce_message_hook** (` | `)`; |   |

| `void **register_core_generate_soft_bounce_message_hook_first** (` | <var class="pdparam">hook</var>, |   |
|   | <var class="pdparam">closure</var>`)`; |   |

`ec_hook_core_generate_soft_bounce_message_func_t <var class="pdparam">hook</var>`;
`void *<var class="pdparam">closure</var>`;

| `void **register_core_generate_soft_bounce_message_hook_last** (` | <var class="pdparam">hook</var>, |   |
|   | <var class="pdparam">closure</var>`)`; |   |

`ec_hook_core_generate_soft_bounce_message_func_t <var class="pdparam">hook</var>`;
`void *<var class="pdparam">closure</var>`;

| `email_message* **call_core_generate_soft_bounce_message_hook** (` | <var class="pdparam">message</var>`)`; |   |

`email_message * <var class="pdparam">message</var>`;<a name="idp18730368"></a>
## Description

This hook allows the normal mailer delivery notification (a.k.a. bounce) message to be customized. The subject email is passed as parameter *`message`* and the registered function may choose to construct and return a valid `email_message` structure containing the desired attributes and body. If NULL is returned, the next registered function is invoked.

Constructing an entire email_message can be overly complicated if the goal is only a replacement of the preamble of the message. Preamble replacement can be accomplished via the `generate_soft_bounce_message_preamble` hook.

| [Prev](hooks.core.generate_rfc3464_message_preamble.php)  | [Up](hooks.core.php) |  [Next](hooks.core.generate_soft_bounce_message_preamble.php) |
| generate_rfc3464_message_preamble  | [Table of Contents](index.php) |  generate_soft_bounce_message_preamble |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)