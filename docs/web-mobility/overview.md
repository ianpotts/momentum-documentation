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

| Chapter 1. Overview of Mobile Momentum |
| [Prev](p.smpp.php)  | Part I. Mobile Momentum SMPP |  [Next](overview.smppesme.php) |

## Chapter 1. Overview of Mobile Momentum

**Table of Contents**

<dl class="toc">

<dt>[1.1\. Architecture](overview.php#overview-architecture)</dt>

<dt>[1.2\. The Short Message Peer-to-Peer Protocol (SMPP) ESME Module](overview.smppesme.php)</dt>

<dt>[1.3\. Message Conversions, Transformations, and Mappings](overview-SmppEmailSMS.php)</dt>

<dt>[1.4\. Installing Momentum](overview.installing.php)</dt>

</dl>

Mobile Momentum is a set of additional features for the Momentum core enabling interoperability of Internet email and Short Message Service (SMS) text messaging. In the most basic use case, email senders may address an email to an SMS capable telephone as:

`4445551234@somewhere.com`

In this case, `somewhere.com` is an appropriately configured Mobile Momentum domain. An example configuration is given in [Section 5.1, “SMSC Bind Parameters”](mobility.best.practices.php#mobility.best.practices.bind.params "5.1. SMSC Bind Parameters").

Mobile Momentum can also convert mobile phone SMS text messages *to* email. An SMS text messages sent to a telephone number can be converted to email by supplying the destination email address and an optional subject header (in parenthesis) at the beginning of the text message. This case is shown below:

```
user@example.com(subject text) This is an SMS message text to be sent
as email to user@example.com.
```

## 1.1. Architecture

This section describes the Mobile Momentum architecture and how it fits in with the Momentum core architecture. Mobile Momentum builds upon the Momentum core, preserving all existing Momentum core capabilities. The Mobile Momentum architecture consists of three primary architectural components extending the Momentum core:

*   The mobility modules discussed in [Chapter 2, *Mobile Momentum SMPP*](momentum.mobility.php "Chapter 2. Mobile Momentum SMPP") 

*   The multi-message module discussed in and in [Chapter 7, *Mobile Momentum MM7*](mobility.mm7.php "Chapter 7. Mobile Momentum MM7") .

*   [Section 1.2, “The Short Message Peer-to-Peer Protocol (SMPP) ESME Module”](overview.smppesme.php "1.2. The Short Message Peer-to-Peer Protocol (SMPP) ESME Module")

The Short Message Peer-to-Peer Protocol/External Short Messaging Entity (SMPP/ESME) module implements the ESME, or client side of the SMPP protocol and also connection management functions. Email/SMS conversion functions include address mappings, and message content transformations such as encodings and the interworking format. (See [Section 1.3.1, “Email/SMS Interworking Format”](overview-SmppEmailSMS.php#overview-SMPPInterworkingFormat "1.3.1. Email/SMS Interworking Format") for more details.)

### 1.1.1. SMPP Domains and Bindings

Mobile Momentum SMS messaging configuration parameters are specified within the existing Momentum `domain` and `binding` stanzas. Domain and binding stanzas within the configuration file contain the operational parameters for controlling and messaging on SMTP and SMPP connections. A domain stanza supporting SMS messaging is called an `SMPP domain`. An SMPP domain within the Momentum configuration file activates the SMPP/ESME module and Email/SMS conversion functions.

An SMPP domain is defined by including the `SMPP_SMSC_Server` configuration parameter within the scope of the domain stanza. Just as in SMTP, Momentum binding stanzas may refer to SMPP domain stanzas to refine or specialize parameter specifications provided by the SMPP domain stanza. The main difference between SMPP and SMTP domains is that SMTP domains handle only message transmission, while SMPP domains provide for both transmitting and receiving. This is because an SMTP client may only transmit messages, while an SMPP client may both transmit and receive messages on the same connection. An SMTP server is necessary for receiving messages with SMTP. The SMTP listener stanza contains the parameters defining the SMTP server operations for receiving messages over SMTP. Mobile Momentum does not provide an SMPP server implementation, so there is no listener stanza for SMPP.

| [Prev](p.smpp.php)  | [Up](p.smpp.php) |  [Next](overview.smppesme.php) |
| Part I. Mobile Momentum SMPP  | [Table of Contents](index.php) |  1.2. The Short Message Peer-to-Peer Protocol (SMPP) ESME Module |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)