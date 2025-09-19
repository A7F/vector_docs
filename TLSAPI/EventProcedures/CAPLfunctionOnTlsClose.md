[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/EventProcedures/CAPLfunctionOnTlsClose.md)

[CAPL Functions](../../CAPLfunctions.md) » [TLS API](../CAPLfunctionsTLSOverview.md) » OnTlsClose

# OnTlsClose

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnTlsClose(dword socketHandle, int result);
```

## Description

If the CAPL program implements this callback it is called when the peer closes the tls connection while a receive call is pending.

## Parameters

- **socket**: The TLS socket handle. If the handle is valid (not equal to ~0), it corresponds to the socket that was used for [tlsOpen](../Functions/CAPLfunctiontlsOpen.md).
- **result**: The specific TLS [result code](../Functions/CAPLfunctiontlsGetLastError.md). If the peer has closed the connection, the result is 4 (PeerClosed).

## Return Values

—

## Example

```plaintext
void OnTlsClose(dword socketHandle, int result)
{
  if(result == 4)
  {
    write("peer closed tls connection");
    TlsClose(socketHandle, 1);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
