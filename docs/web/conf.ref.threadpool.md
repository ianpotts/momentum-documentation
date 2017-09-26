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

| threadpool |
| [Prev](conf.ref.tcp_buffer_size.php)  | 9.2. Configuration Files and Option Details |  [Next](conf.ref.timestampformat.php) |

<a name="conf.ref.threadpool"></a>
## Name

threadpool — configure thread pool specific options

<a name="conf.ref.threadpool.description"></a>
## Description

```
ThreadPool "SwapOut" {
  Concurrency = 5
}

ThreadPool "SwapIn" {
  Concurrency = 5
}

ThreadPool "Unlink" {
  Backlog = 100
  Concurrency = 6
}

ThreadPool "Batch_Unlink" {
  Concurrency = 4
}

ThreadPool "Close" {
  Concurrency = 0
}

ThreadPool "CPU" {
  Concurrency = 4
}

ThreadPool "IO" {
  Concurrency = 50
}

ThreadPool "SpoolIn" {
  Concurrency = 1
}
```

**Configuration Change. ** This feature is available starting from Momentum 2.2.

Momentum uses a combination of asynchronous IO and thread pools to efficiently manage its workload. There are a number of predefined thread pools for different classes of work. It is not possible to prioritize work within a pool (jobs are queued as FIFO), but it is possible to create a pool for jobs that have different relative priorities, so that long running jobs won't starve more important short-lived jobs.

The `ThreadPool` stanza allows you to define or modify thread pool characteristics. The standard thread pools are listed above, along with their defaults, and you may also define new pools simply by specifying the name of the pool. Creating new pools isn't very useful unless you assign jobs to the pool; various modules allow you to specify alternate pools for their tasks so that you can more effectively prioritize the tasks in your environment.

There are three basic attributes for a thread pool in Momentum version 2.2 and higher:

<dl class="variablelist">

<dt>`Concurrency`</dt>

<dd>

The concurrency defines the number of threads in the pool. Sizing a pool correctly is important to avoid torturing your system. If the pool is intended to be used for CPU intensive work, the ideal size is approximately the number of cores that you want to assign to the work. If you raise the concurrency of such a pool too high, you will cause increased context switching and degrade overall system performance.

If the pool is intended to be used for blocking IO operations, where the threads are expected to be mostly sleeping, you will usually want to increase the number of threads to a magic number that gets the most throughput for your system. Setting this number too high can increase context switching, and with heavily IO bound tasks, can increase disk thrashing.

You should also note that each thread requires its own stack space; creating too many threads can consume large portions of your address space, particularly on a 32-bit system. Some versions of Linux/glibc allocate 10MB per thread by default, which can quickly consume your entire address space. You can reduce the impact of this problem by setting the thread pool stack size (see below).

### Note

If you use the [csapi module](modules.csapi.php "14.18. csapi – The Content Scanning API Module") be sure to set the concurrency of the CPU threadpool to a value that is less than the max_concurrency of the csapi module.

</dd>

<dt>`Stack_Size`</dt>

<dd>

As mentioned above, each thread in the system requires its own stack space. The default amount used is system dependent and is usually very much higher than the amount you will need per thread. If you find that you need to increase the number of threads, you may also want to define a smaller Stack_Size so that you don't use so much of your address space or RAM.

The amount of stack space you need for a given pool varies depending on the usage patterns for that pool. Some jobs will need more stack space than others. You should exercise caution when adjusting the stack size, setting it too small can cause a stack overflow which can lead to memory corruption and ultimately a crash.

The stack size can be changed at runtime, but only affects newly spawned threads.

</dd>

<dt>`Backlog`</dt>

<dd>

The backlog setting affects the maximum number of jobs that can be queued up for a pool. Most pools will not have a limit, but some tasks require a braking effect if the system can't satisfy the workload in time.

For instance, the transactional nature of SMTP requires that messages are unlinked from the spool "immediately" after the receipt of successful delivery so that duplicate delivery can not occur if the power were to fail. Since the unlink call is a blocking operation, it is pushed to the `Unlink` pool for processing. If the unlink pool backlog were to grow without bound, there is increasing risk of sending a great many duplicate deliveries when the server restarts after a power failure.

To mitigate this risk, we put a limit on the maximum length of the queue; if pushing a job to the queue would exceed the length, then the caller will block until the queue is small enough.

If you find that you need to change the Backlog size for the Unlink pool, you should investigate why your disks cannot keep up; make sure that you aren't logging to the same spindles as your spool, and examine the tuning options for those filesystems.

When using the custom_logger module, in some circumstances you may find it necessary to create a thread pool so that you can explicitly define its backlog option. For more information see [Section 14.19, “custom_logger – Customizable Logging”](modules.custom_logger.php "14.19. custom_logger – Customizable Logging").

The backlog cannot be changed at runtime.

</dd>

</dl>

<a name="idp6891440"></a>
## Scope

ThreadPool is valid in the global scope.

<a name="idp6893072"></a>
## See Also

[domain](conf.ref.domain.php "domain"), [host](conf.ref.host.php "host"), [Section 2.4, “Configuration Scopes and Fallback”](ecelerity.conf.fallback.php "2.4. Configuration Scopes and Fallback"), [threads](console_commands.threads.php "threads")

| [Prev](conf.ref.tcp_buffer_size.php)  | [Up](conf.ref.files.php) |  [Next](conf.ref.timestampformat.php) |
| tcp_buffer_size  | [Table of Contents](index.php) |  timestampformat |

Follow us on:

[![Facebook](https://support.messagesystems.com/images/icon-facebook.png)](http://www.facebook.com/messagesystems) [![Twitter](https://support.messagesystems.com/images/icon-twitter.png)](http://twitter.com/#!/MessageSystems) [![LinkedIn](https://support.messagesystems.com/images/icon-linkedin.png)](http://www.linkedin.com/company/message-systems)