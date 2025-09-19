[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/EventProcedures/CAPLfunctionOnTlsHandshakeComplete.md)

**CAPL Functions** » **TLS API** » **OnTlsHandshakeComplete**

# OnTlsHandshakeComplete

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void OnTlsHandshakeComplete(dword socket, long result);
```

## Description

If the CAPL program implements this callback it is called when a **TLS** handshake is completed.

## Parameters

- **socket**: The TLS socket handle. If the handle is valid (not equal to ~0), it corresponds to the socket that was used for [tlsOpen](../Functions/CAPLfunctiontlsOpen.md).
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is an error code.

## Return Values

—

## Example

```plaintext
void OnTlsHandshakeComplete(dword socket, long result)
{
  LONG retVal;
  if (result == 0)
  {
    gConnectionSecured = 1;

    //
    // Send first message
    //
    retVal = TcpSend( socket, "The TLS connection is up", 25 );

    if (retVal != 0)
    {
      // an error occurred
      return;
    }

    //
    // Receive
    //
    TcpReceive( socket, gRecBuffer, elcount(gRecBuffer) );
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
