[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimDisconnectFromServer.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMDisconnectFromServer

# Iso11783IL_TIMDisconnectFromServer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMDisconnectFromServer(dbNode server); // form 1`
- `long Iso11783IL_TIMDisconnectFromServer(byte serverAddress); // form 2`
- `long Iso11783IL_TIMDisconnectFromServer(dbNode server, dword options); // form 3`
- `long Iso11783IL_TIMDisconnectFromServer(bytes serverAddress, dword options); // form 4`
- `long Iso11783IL_TIMDisconnectFromServer(dbNode client, dbNode server); // form 5`
- `long Iso11783IL_TIMDisconnectFromServer(dbNode client, bytes serverAddress); // form 6`
- `long Iso11783IL_TIMDisconnectFromServer(dbNode client, dbNode server, dword options); // form 7`
- `long Iso11783IL_TIMDisconnectFromServer(dbNode client, bytes serverAddress, dword options); // form 8`

## Description

Stops TIM connection to a TIM server. Releases the communication with a connected TIM server.

## Parameters

- **server**: The client releases the connection to the TIM server specified by this node.
- **serverAddress**: The client releases the connection to the TIM server with this address.
- **options**: Additional options.
  - **Graceful shutdown**: `01h` - Client gracefully shutdowns connection to the specified server.
- **client**: TIM client node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)