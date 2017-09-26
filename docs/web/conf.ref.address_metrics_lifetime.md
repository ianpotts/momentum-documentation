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

| address_metrics_lifetime |
| [Prev](conf.ref.address_metrics_cleanse_interval.php)  | 9.2. Configuration Files and Option Details |  [Next](conf.ref.alias_schemes.php) |

<a name="conf.ref.address_metrics_lifetime"></a>
## Name

address_metrics_lifetime — the TTL of address metrics

## Synopsis

`Address_Metrics_Lifetime = 1800`

<a name="idp4066624"></a>
## Description

Address metrics store data on the quality of service to a particular target host from a particular binding; data such as the time since the last failure, and how long it takes to connect and to deliver a message. Address metrics are used to determine which of a domain's MXs to open more connections to. The address_metrics_lifetime option controls how long a set of address metrics will live after last being updated. Normally this option does not need to be changed.

The default value for this option is 1800 seconds.

<a name="idp4069200"></a>
## Scope

Address_Metrics_Lifetime is valid in the global scope.

<a name="idp4070848"></a>
## See Also

[address_metrics_cleanse_interval](conf.ref.address_metrics_cleanse_interval.php "address_metrics_cleanse_interval")

| [Prev](conf.ref.address_metrics_cleanse_interval.php)  | [Up](conf.ref.files.php) |  [Next](conf.ref.alias_schemes.php) |
| address_metrics_cleanse_interval  | [Table of Contents](index.php) |  alias_schemes |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)