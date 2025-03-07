[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimActivateServer.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMActivateServer

# Iso11783IL_TIMActivateServer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
If [Iso11783IL_ControlInit](CAPLfunctionIso11783ILControlInit.md) is not called on measurement start then the TIM Server starts claiming its address. TIM Server functionality is activated if `Iso11783IL_TIMActivateServer` is called.

## Function Syntax

```plaintext
long Iso11783IL_TIMActivateServer(); // form 1
long Iso11783IL_TIMActivateServer(dbNode server); // form 2
```

## Description

Activates the TIM server which starts transmitting the cyclic message **TIM_ServerStatus_Msg**.

## Parameters

- **server**: TIM server node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)