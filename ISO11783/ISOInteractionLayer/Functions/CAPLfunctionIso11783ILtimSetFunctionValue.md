[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetFunctionValue.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetFunctionValue

# Iso11783IL_TIMSetFunctionValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMSetFunctionValue(byte functionId, word rawValue); // form 1`
- `long Iso11783IL_TIMSetFunctionValue(dbNode server, byte functionId, word rawValue); // form 2`

## Description

Sets the value of a TIM function. This value is transmitted in the status message of the TIM function.

## Parameters

- **functionID**: ID of the function.
  - **Function ID**: Description
    - 1-32 (1h-20h): Auxiliary Value 1 – 32
    - 64 (40h): Front PTO
    - 65 (41h): Rear PTO
    - 66 (42h): Front hitch
    - 67 (43h): Rear hitch
    - 68 (44h): Vehicle speed
    - 70 (46h): External guidance
- **rawValue**: New raw value of the TIM function.
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