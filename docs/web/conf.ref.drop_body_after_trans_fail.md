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

| drop_body_after_trans_fail |
| [Prev](conf.ref.domainkeys.php)  | 9.2. Configuration Files and Option Details |  [Next](conf.ref.ehlo_hostname.php) |

<a name="conf.ref.drop_body_after_trans_fail"></a>
## Name

drop_body_after_trans_fail — number of retry attempts before freeing message memory

## Synopsis

`drop_body_after_trans_fail = 3`

<a name="idp5062816"></a>
## Description

Momentum aggressively attempts to keep messages in memory, to avoid reading their contents from disk. For domains which have a large number of transient failures, or for which messages often remain for a long time in the queue, this can have abusive effects on memory usage. To counter this, Momentum allows you to specify a threshold of transient failures after which Momentum will not store the message in memory, but instead always read it from disk. To force Momentum to read from disk all messages that have had any transient failures, set this value to 0.

The default value for this option is 3 attempts.

<a name="idp5065488"></a>
## Scope

drop_body_after_trans_fail is valid in the binding, binding_group, domain and global scopes.

| [Prev](conf.ref.domainkeys.php)  | [Up](conf.ref.files.php) |  [Next](conf.ref.ehlo_hostname.php) |
| domainkeys  | [Table of Contents](index.php) |  ehlo_hostname |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)