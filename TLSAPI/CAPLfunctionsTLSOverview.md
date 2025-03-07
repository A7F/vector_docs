[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/CAPLfunctionsTLSOverview.md)

## TLS CAPL Functions

[CAPL Functions](../CAPLfunctions.md) » TLS CAPL Functions

**Valid for:** CANoe DE • CANoe4SW DE

The TLS API provides functions for encrypting a socket connection (see [TCP/IP CAPL Functions](../TCPIPAPI/CAPLfunctionsTCPIPOverview.md)).

Please be aware that the following CAPL functions can only be used when there is no AUTOSAR Eth or SOME/IP interaction layer assigned. Otherwise, you have to use the corresponding functions defined in the AUTOSAR Eth or SOME/IP interaction layer for TLS.

To use the CAPL [Transport Layer Security](../../CANoeCANalyzer/Security/SecurityTLS.md) (TLS) functions, you must add a profile in the [Vector Security Manager](javascript:startCANoeSubToolLauncherEN('Security Manager','HELP:VectorSecurityManager.md')). This TLS profile is used in the [tlsAuthenticateAsClientWithConfiguration](Functions/CAPLFunctiontlsAuthenticateAsClientWithConfiguration.md) and [tlsAuthenticateAsServerWithConfiguration](Functions/CAPLFunctiontlsAuthenticateAsServerWithConfiguration.md) functions.

Please also use the sample configuration [TCP Chat (CAPL) with TLS encryption](../../SampConf/Ethernet/CANoe/Chat/ChatTLScn.md) for reference.

---

### Functions

- [HasEarlyDataBeenAccepted](Functions/CAPLFunctionHasEarlyDataBeenAccepted.md): To check if the early data has been accepted by the TLS 1.3 server, this function should be called, but only after a successful TLS handshake.

- [tlsAuthenticateAsClientWithConfiguration](Functions/CAPLFunctiontlsAuthenticateAsClientWithConfiguration.md): Starts the (D)TLS authentication handshake as client.

- [tlsAuthenticateAsClientWithConfigurationAndEarlyData](Functions/CAPLFunctiontlsAuthenticateAsClientWithConfigurationAndEarlyData.md): TLS 1.3 allows clients to send encrypted data to the server right after the ClientHello message on the first flight ("early data") with the performance-enhancing feature zero round trip time resumption (0-RTT).

- [tlsAuthenticateAsServerWithConfiguration](Functions/CAPLFunctiontlsAuthenticateAsServerWithConfiguration.md): Starts the (D)TLS authentication handshake as server.

- [tlsClose](Functions/CAPLfunctiontlsClose.md): Closes a TLS socket.

- [tlsGetLastError](Functions/CAPLfunctiontlsGetLastError.md): Returns the TLS error code of the last operation that failed on a specified TLS socket.

- [tlsGetLastErrorAsString](Functions/CAPLfunctiontlsGetLastErrorAsString.md): Retrieves the error message of the last operation that failed on a specified TLS socket.

- [tlsOpen](Functions/CAPLfunctiontlsOpen.md): Opens a TLS socket.

### Callbacks

- [OnDtlsServerConnect](EventProcedures/CAPLfunctionOnDtlsServerConnect.md): This callback is called when a new DTLS client connects to the DTLS server.

- [OnObservedAndDecryptedTlsApplicationData](EventProcedures/CAPLfunctionOnObservedAndDecryptedTlsApplicationData.md): This callback is called when observed and decrypted TLS application data is available.

- [OnObservedAndDecryptedTlsHandshakeData](EventProcedures/CAPLfunctionOnObservedAndDecryptedTlsHandshakeData.md): This callback is called when observed TLS handshake data is available.

- [OnTlsClose](EventProcedures/CAPLfunctionOnTlsClose.md): This callback is called when the peer closes the TLS connection while a receive call is pending.

- [OnTlsEarlyDataReceived](EventProcedures/CAPLfunctionOnTlsEarlyDataReceived.md): To handle early data from the TLS 1.3 client, the CAPL server program must implement this callback.

- [OnTlsHandshakeComplete](EventProcedures/CAPLfunctionOnTlsHandshakeComplete.md): This callback is called when a TLS socket completes its handshake.

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)