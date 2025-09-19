[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimConnectToServer.md)

### CAPL Functions » ISO11783 » ISO11783 Interaction Layer » Iso11783IL_TIMConnectToServer

# Iso11783IL_TIMConnectToServer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
If [ISO11783IL_ControlInit](CAPLfunctionIso11783ILControlInit.md) is not called on measurement start then the TIM Client starts claiming its address. TIM Client functionality is activated if `Iso11783IL_TIMConnectToServer` is called.

## Function Syntax

- `long Iso11783IL_TIMConnectToServer(dbNode server); // form 1`
- `long Iso11783IL_TIMConnectToServer(byte serverAddress); // form 2`
- `long Iso11783IL_TIMConnectToServer(dbNode client, dbNode server); // form 3`
- `long Iso11783IL_TIMConnectToServer(dbNode client, byte serverAddress); // form 4`

## Description

Starts a TIM connection to a TIM server.

Starts initialization with a server by switching to state **Automaton unavailable** and waits for the status message of the server.

## Parameters

- **server**: The client connects to the TIM server specified by this node.
- **serverAddress**: The client connects to the TIM server with this address.
- **client**: TIM client node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
