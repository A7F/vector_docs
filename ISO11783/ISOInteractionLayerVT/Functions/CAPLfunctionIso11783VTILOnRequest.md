[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILOnRequest.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_OnRequest**

# VTIL_OnRequest (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_OnRequest( long rqPGN, long sourceAddr );
long VTIL_OnRequest( long rqPGN, long sourceAddr, long destinationAddress );
```

## Description

This callback function is called from the VT IL if a request (0xEA00) is received.

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
long VTIL_OnRequest( long rqPGN, long sourceAddr )
{
  switch( rqPGN ) {
  case 0xFF02:
    return 2; // send NACK
  }
  return 1;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)