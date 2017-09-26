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

| 14.33. inbound_audit – Inbound traffic analytics |
| [Prev](modules.icu.php)  | Chapter 14. Modules Reference |  [Next](modules.jlog.php) |

## 14.33. inbound_audit – Inbound traffic analytics

<a class="indexterm" name="idp12194736"></a>

The inbound_audit module provides time-series analytics on the behavior of sending IPs. It is designed to help spot emergent issues, such as abuse, and to provide a mechanism for implementing counter-based policy on IPs. The inbound_audit module differs from the standard analytics available in Momentum in that it allows you to compare short-term real-time data with data from earlier time windows. This makes it easy to spot changes in behavior.

### 14.33.1. Runtime Usage

For more information follow the preceding links.

**Sieve Commands**

Configuring this module makes a number of Sieve commands available. These commands are:

*   [audit_series](sieve.ref.audit_series.php "audit_series") and [audit_series_add](sieve.ref.audit_series_add.php "audit_series_add")

*   [audit_service](sieve.ref.audit_service.php "audit_service") [audit_connections_on_service](sieve.ref.audit_connections_on_service.php "audit_connections_on_service") and [audit_connections_on_listener](sieve.ref.audit_connections_on_listener.php "audit_connections_on_listener")

*   [ec_ip_connections](sieve.ref.ec_ip_connections.php "ec_ip_connections"), [ec_ip_rejections](sieve.ref.ec_ip_rejections.php "ec_ip_rejections") and [ec_ip_receptions](sieve.ref.ec_ip_receptions.php "ec_ip_receptions")

### 14.33.2. Cluster support

This module provides additional cluster-enabled features. In particular, there are clustered versions of the "ec_ip" commands: [ec_ip_connections_cluster](sieve.ref.ec_ip_connections_cluster.php "ec_ip_connections_cluster"), [ec_ip_rejections_cluster](sieve.ref.ec_ip_rejections_cluster.php "ec_ip_rejections_cluster") and [ec_ip_receptions_cluster](sieve.ref.ec_ip_receptions_cluster.php "ec_ip_receptions_cluster"). Also, [audit_series_add](sieve.ref.audit_series_add.php "audit_series_add") can be used in a replicated mode as described in its specific manual page. Replicated audit series allow for recording and acting on arbitrary IP-based events across a cluster. Users of replicated audit_series can also make use of the as_logger (see [Section 14.3, “as_logger – Audit series logger”](modules.as_logger.php "14.3. as_logger – Audit series logger")) module to automatically journal these series on the cluster manager at periodic intervals, allowing for post-analysis using the cluster web console or custom scripts. For more information about replication and inbound audit see [Section 7.5.1.4, “Replicated inbound audit metrics”](cluster.replication.php#cluster.replication.inbound_audit "7.5.1.4. Replicated inbound audit metrics").

### 14.33.3. Configuration

There is no configuration necessary in order to use many features of this module, apart from the module declaration. The definition of "monitors" in the configuration is needed only when using the Sieve commands **ec_ip_connections, ec_ip_rejections** , or **ec_ip_receptions**; or if the "inbound_audit show ip" console command is used.

<a name="example.inbound_audit"></a>

**Example 14.53. inbound_audit module**

```
Validate validate/inbound_audit inbound_audit
{
  # any monitor definitions go here.
  monitor = "300,6"
  monitor = "1800,4"
}
```

Valid configuration parameters are:

<dl class="variablelist">

<dt>log_dir</dt>

<dd>

The directory where audit series with the serialized flag set are stored. The default value for this option is `/var/log/ecelerity/audit_series_logs`.

</dd>

<dt>maintenance_interval</dt>

<dd>

The default value for this option is `300`.

</dd>

<dt>monitor = "window-size,number-of-windows"</dt>

<dd>

Create a monitoring window *window-size* seconds long, and maintain *number-of-windows* windows historically. In the example above, we create two different time-series: 5 minutes for the past half hour, and 30 minutes for the past 2 hours.

</dd>

<dt>serialize_dir</dt>

<dd>

The directory where the audit series state is persisted on shutdown and read in on startup. The default value for this option is `/var/log/ecelerity/audit_series_persist`.

</dd>

</dl>

### 14.33.4. inbound_audit Management Using Console Commands

The inbound_audit module can be queried through the `ec_console`; the following commands are available:

**14.33.4.1. The show ip Command**inbound_audit:*`instance_name`* show ip ip[/mask]

This command dumps all collected time-series data for the specified IP/netblock.

When you query the inbound_audit module's time-series data, you get back data formatted as follows:

```
10:45:03 ecelerity(/tmp/2025)> inbound_audit show ip 10.0.0.0/8
Connections 1800/0: 30
Connections 1800/1: 0
Connections 1800/2: 0
Connections 1800/3: 0
Connections 1800/4: 0
Receptions 1800/0: 1697
Receptions 1800/1: 0
Receptions 1800/2: 0
Receptions 1800/3: 0
Receptions 1800/4: 0
Rejections 1800/0: 0
Rejections 1800/1: 0
Rejections 1800/2: 0
Rejections 1800/3: 0
Rejections 1800/4: 0
```

The fields for this output are:

*   **type of data** 

    The type is either connections made, messages received or messages rejected.

*   **window size/window offset** 

    The size of the window being displayed, plus the number of the window. For example `300/0` is the current 5 minute window, while `300/2` is the 5 minute window that occurred 10 minutes ago (i.e 2 windows before the current window).

*   **count**

    The number of events of the specified type that occurred during that window.

**14.33.4.2. The help Command**

**Configuration Change. ** This feature is available starting from Momentum 2.2.2.45.

inbound_audit:*`instance_name`* help

Show the available commands.

```
show ip <ip[/mask]>
    Display verbose statistics for the specified ip or cidr block
delete_ip <ip> <series> <parameters>
    Delete an IP from a defined named series
count_cidr <ip[/mask]> <series> <parameters> <period_start> <period_end>
    Count a CIDR in a named series
add <series> <parameters> <ip> <increment>
    Add a value to a CIDR in a named series
subtract <series> <parameters> <ip> <decrement>
    Subtract a value from a CIDR in a named series
show all
    Display verbose statistics for all domains as a CSV list
load <series> <filename>
    Load a series from a file.  The the filename can be omitted if
    the file has the same name as the series
```
**14.33.4.3. The delete_ip Command**

**Configuration Change. ** This feature is available starting from Momentum 2.2.2.45.

inbound_audit:*`instance_name`* delete_ip *`ip`* *`series`* *`parameters`*

Delete an IP from a defined named series.

**14.33.4.4. The count_cidr Command**

**Configuration Change. ** This feature is available starting from Momentum 2.2.2.45.

inbound_audit:*`instance_name`* count_cidr *`ip[/mask] series parameters period_start period_end`*

Count a CIDR in a named series.

**14.33.4.5. The add Command**

**Configuration Change. ** This feature is available starting from Momentum 2.2.2.45.

inbound_audit:*`instance_name`* add *`series parameters ip increment`*

Add a value to a CIDR in a named series.

**14.33.4.6. The subtract Command**

**Configuration Change. ** This feature is available starting from Momentum 2.2.2.45.

inbound_audit:*`instance_name`* subtract *`series parameters ip decrement`*

Subtract a value from a CIDR in a named series.

**14.33.4.7. The show all Command**

**Configuration Change. ** This feature is available starting from Momentum 2.2.2.45.

inbound_audit:*`instance_name`* show all

Display verbose statistics for all domains as a CSV list.

**14.33.4.8. The load Command**

**Configuration Change. ** This feature is available as of version 2.2.3.46.

inbound_audit:*`instance_name`* load *`series`* *`filename`*

Load a series from a file. The filename can be omitted if the file has the same name as the series.

| [Prev](modules.icu.php)  | [Up](modules.php) |  [Next](modules.jlog.php) |
| 14.32. icu – ICU  | [Table of Contents](index.php) |  14.34. jlog – The jlog Module |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)