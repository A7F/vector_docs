[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimRestartAuthentication.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMRestartAuthentication

# Iso11783IL_TIMRestartAuthentication

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMRestartAuthentication(dbNode server);` // form 1
- `long Iso11783IL_TIMRestartAuthentication(byte serverAddress);` // form 2
- `long Iso11783IL_TIMRestartAuthentication(dbNode client, dbNode server);` // form 3
- `long Iso11783IL_TIMRestartAuthentication(dbNode client, byte serverAddress);` // form 4

## Description

This function restarts the authentication process of a client/server communication.

The client restarts the authentication by setting the (Re)Start authentication status bit of the **Auth_ClientAuthenticationStatusClient** message.

This function only succeeds if the authentication process is currently active (especially if current state is Authentication error).

## Parameters

- **server**: The CAPL function restarts authentication for the connection to this server.
- **serverAddress**: The CAPL function restarts authentication for the connection to the server with this address.
- **client**: TIM client node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
