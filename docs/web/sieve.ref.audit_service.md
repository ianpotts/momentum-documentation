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

| audit_service |
| [Prev](sieve.ref.audit_series_add.php)  | Chapter 15. Sieve++ Function Reference |  [Next](sieve.ref.brightmail.php) |

<a name="sieve.ref.audit_service"></a>
## Name

audit_service — Return how many connections currently are established from a CIDR block to an arbitrary service

## Synopsis

`audit_service` { *`service_name`* } { *`address/mask`* }

<a name="idp13342864"></a>
## Description

`audit_service` returns a stringlist containing a single member, which is a string containing the number of connections the CIDR block provided currently has established to the provided service. If the provided service is "SMTP" then the behavior is identical to `audit_connections_on_service`. If you have the cluster module loaded, then you can query the "inbound_cidr" service to audit connections to the whole cluster instead of just one server. In the address/mask argument, address may be omitted to cause the action to use the current IP address instead. In that case, one could provide an argument of "/32" or "/24" to get the current connections for the IP address currently connecting or for the /24 CIDR block of the IP address currently connecting.

Services that may be audited are:

*   `ECStream`

*   `SMTP`

*   `Control`

*   `ECmmove2` (The service that handles duravip message moves.)

*   `ECCluster`

*   `inbound_cidr`

### Note

This feature requires the inbound_audit module. See [Section 14.33, “inbound_audit – Inbound traffic analytics”](modules.inbound_audit.php "14.33. inbound_audit – Inbound traffic analytics") for more information.

<a name="example.audit_service"></a>

**Example 15.10. audit_service example**

```
($connections) = audit_service "inbound_cidr" "/32";
($c_connections) = audit_service "inbound_cidr" "/24";
if ec_test :value "gt" :comparator "i;ascii-numeric" "${connections}" "1000" {
  ec_tarpit 10 "too many connections /32";
}

if ec_test :value "gt" :comparator "i;ascii-numeric" "${c_connections}" "10000" {
  ec_tarpit 10 "too many connections /24";
}
```

| [Prev](sieve.ref.audit_series_add.php)  | [Up](sieve.ref.php) |  [Next](sieve.ref.brightmail.php) |
| audit_series_add  | [Table of Contents](index.php) |  brightmail |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)