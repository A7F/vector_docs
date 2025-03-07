[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILOnRequest.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILOnRequest

# J1939ILOnRequest (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILOnRequest( long rqPGN, long sourceAddr )
long J1939ILOnRequest( long rqPGN, long sourceAddr, long destinationAddress )
```

## Description

This callback function is called from the J1939 IL if a request (0xEA00) is received.

## Parameters

- **rqPGN**: requested PGN
- **sourceAddr**: source address from which the request was sent
- **destinationAddress**: destination address on which the request was sent

## Return Values

- **0**: do not respond to the request
- **1**: request with the message from the Tx list of the node
- **2**: send a negative acknowledgment (NACK)
- **3**: send a positive acknowledgment (ACK)

## Example

```plaintext
LONG J1939ILOnRequest( LONG rqPGN, LONG sourceAddr )
{
  switch( rqPGN ) {
    case 0xFF02:
      return 2; // send NACK
  }
  return 1;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)