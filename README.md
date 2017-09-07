httpstime
=========

Simple bash script to set the system time via HTTPS.
Born out of frustration with all other existing solutions, see also:

* https://blog.hboeck.de/archives/890-In-Search-of-a-Secure-Time-Source.html

By default it will use the HTTP Date header from www.google.com to
set the time. Alternatively another hostname can be passed on the
command line.

Unlike NTP setting the time via HTTPS provides protection against
man in the middle attacks.

The accuracy is worse than NTP, as the time resolution is only
in seconds and network transmission times aren't considered.

Security considerations
=======================

This provides no protection against rogue Google servers sending
a bad time.

In theory the server could try to attack the parser in the "date"
tool. However I tested it with american fuzzy lop and it seems
robust.
