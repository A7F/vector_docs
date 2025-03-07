[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILOnRequest.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_OnRequest

# FSIL_OnRequest (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_OnRequest( long rqPGN, long sourceAddr );
long FSIL_OnRequest( long rqPGN, long sourceAddr, long destinationAddress );
```

## Description

Is called if a request (0xEA00) is received. The return value defines the node reaction to the request.

## Parameters

- **rqPGN**: Requested PGN
- **sourceAddr**: Source address from which the request was sent
- **destinationAddress**: Destination address on which the request was sent

## Return Values

- **0**: Do not respond to the request
- **1**: Request with the message from the Tx list of the node
- **2**: Send a negative acknowledgment (NACK)
- **3**: Send a positive acknowledgment (ACK)

## Example

```plaintext
long FSIL_OnRequest( long rqPGN, long sourceAddr )
{
  switch( rqPGN ) {
  case 0xFF02:
    return 2; // send NACK
  }
  return 1;
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)