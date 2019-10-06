
Step 1: Testing Connectivity to a Server
****************************************

.. module:: sslyze.server_connectivity_tester

Basic Example
=============

Before a server can be scanned, SSLyze must ensure that it is able to reach the server. This is achieved using the
`ServerConnectivityTester` class:

.. literalinclude:: ../api_sample.py
   :pyobject: demo_server_connectivity_tester

If the call to `ServerConnectivityTester.perform()` is successful, it returns a `ServerConnectivityInfo` object that
can then be used for scanning the server. This is described in :doc:`running-scan-commands`.

Advanced Usage
==============

The `ServerConnectivityTester` classs provides fine-grained controls regarding how SSLyze should connect to a server. If
only a hostname is supplied (like in the example above), default values will be used and SSLyze will assume that the
server is an HTTPS server listening on port 443.

Several additional settings can be supplied in order to be more specific about the protocol the SSL/TLS server uses
(such as StartTLS) and how to connect to it (for example by supplying an IP address or a client certificate).

The ServerConnectivityTester class
----------------------------------

.. autoclass:: ServerConnectivityTester()
   :members: __init__, perform
.. autoclass:: ServerConnectivityError()
.. autoclass:: ServerRejectedConnection()
.. autoclass:: ConnectionToServerTimedOut()
.. autoclass:: ServerHostnameCouldNotBeResolved()
.. autoclass:: ServerTlsConfigurationNotSuportedError()
.. autoclass:: ProxyConnectivityError()

Enabling StartTLS and other supported protocols
-----------------------------------------------

.. module:: sslyze.ssl_settings
.. autoclass:: TlsWrappedProtocolEnum
   :undoc-members:
   :members:

Running scan commands through a proxy
-------------------------------------

.. autoclass:: HttpConnectTunnelingSettings()
   :members: __init__, from_url

Enabling client authentication
------------------------------

.. autoclass:: ClientAuthenticationCredentials()
   :members: __init__

.. module:: nassl.ssl_client
.. autoclass:: OpenSslFileTypeEnum
   :undoc-members:
   :members:

The ServerConnectivityInfo class
--------------------------------

.. module:: sslyze.server_connectivity_info
.. autoclass:: ServerConnectivityInfo()
   :undoc-members:
   :members:
