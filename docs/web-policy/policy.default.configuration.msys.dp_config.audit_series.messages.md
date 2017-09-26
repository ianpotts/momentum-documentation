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

| 4.15. msys.dp_config.audit_series.messages |
| [Prev](policy.default.configuration.msys.dp_config.audit_series.invalid_recipients.php)  | Chapter 4. Configuration Details |  [Next](policy.default.configuration.msys.dp_config.audit_series.spam_mailfrom.php) |

## 4.15. msys.dp_config.audit_series.messages

This configuration table limits the message rate.

Find below the sample excerpt included in the `dp_config.lua` file.

```
msys.dp_config.audit_series.messages = {
  type = "cidr",
  interval = 900,
  buckets = 4,
  thresholds = {
    { check = true,
      key = "/32",
      startv = 0,
      endv = 3,
      threshold = 200,
      honor_whitelist = { "global" } },
    { check = true,
      key = "/24",
      startv = 0,
      endv = 3,
      threshold = 2000,
      honor_whitelist = { "global" } }
  },
  options = {
    persist = true
  }
};
```

The elements of this configuration table are as follows:

<dl class="variablelist">

<dt>type</dt>

<dd>

Legal values for this element are `cidr` and, as of version 3.4, `cidr_ipv6`.

</dd>

<dt>interval</dt>

<dd>

The time interval that you wish to look at measured in seconds. A reasonable value might be `900`.

</dd>

<dt>buckets</dt>

<dd>

A bucket is a window of time of the length defined by "interval". A reasonable value might be `4`.

</dd>

<dt>thresholds</dt>

<dd>

Define the different threshold maximums. `thresholds` is a nested table within this configuration option. The following list defines the attributes of the individual thresholds.

<dl class="variablelist">

<dt>check</dt>

<dd>

Whether or not to use this configuration item.

</dd>

<dt>key</dt>

<dd>

The CIDR mask length for the threshold (the leading forward slash is required).

</dd>

<dt>startv</dt>

<dd>

The starting bucket (0 is the current bucket) to query across.

</dd>

<dt>endv</dt>

<dd>

The ending bucket.

</dd>

<dt>threshold</dt>

<dd>

The threshold that triggers the associated action. In this case a code 421 is issued along with the message `message rate limit exceeded`.

</dd>

<dt>honor_whitelist</dt>

<dd>

A table listing any applicable whitelists set in the `msys.dp_config.whitelist` table.

</dd>

</dl>

</dd>

<dt>options</dt>

<dd>

This item is a table with the following possible keys:

<dl class="variablelist">

<dt>serialize</dt>

<dd>

Write audit series to log. The value may be `true` or `false`; `false` is the default.

When `true`, the log will be written to the directory defined by the `serialize_dir` option in the [inbound_audit](https://support.messagesystems.com/docs/web-ref/modules.inbound_audit.php) module. The default value for this option is `/var/log/ecelerity/audit_series_persist`.

</dd>

<dt>replicate</dt>

<dd>

Defaults to none, but can be `cluster` to send to all nodes, or `manager` to send only to cluster manager nodes. This requires explicit configuration in the `cluster` stanza to operate correctly. For more information see [Data Replication](https://support.messagesystems.com/docs/web-ref/cluster.config.replication.php).

</dd>

<dt>persist</dt>

<dd>

When set to `true`, the audit series will be persisted. The persisted series will be reloaded when the engine restarts. The default value is `false`.

</dd>

</dl>

</dd>

</dl>

| [Prev](policy.default.configuration.msys.dp_config.audit_series.invalid_recipients.php)  | [Up](policy.default.configuration.php) |  [Next](policy.default.configuration.msys.dp_config.audit_series.spam_mailfrom.php) |
| 4.14. msys.dp_config.audit_series.invalid_recipients  | [Table of Contents](index.php) |  4.16. msys.dp_config.audit_series.spam_mailfrom |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)