[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOnRequest.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OnRequest

# Iso11783IL_OnRequest (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OnRequest( long rqPGN, long sourceAddr );
long Iso11783IL_OnRequest( long rqPGN, long sourceAddr, long destinationAddress );
```

## Description

This callback function is called from the ISO11783 IL if a request (0xEA00) is received.

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

```c
LONG Iso11783IL_OnRequest( LONG rqPGN, LONG sourceAddr )
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
