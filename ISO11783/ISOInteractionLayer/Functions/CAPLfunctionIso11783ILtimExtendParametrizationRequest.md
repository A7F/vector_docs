[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimExtendParametrizationRequest.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMExtendParametrizationRequest

# Iso11783IL_TIMExtendParametrizationRequest

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMExtendParametrizationRequest(byte functionId , byte controlMode); // form 1`
- `long Iso11783IL_TIMExtendParametrizationRequest(byte functionId , byte controlMode, dword controlModeDataSize, byte controlModeData[]); // form 2`
- `long Iso11783IL_TIMExtendParametrizationRequest(dbNode client, byte functionId , byte controlMode); // form 3`
- `long Iso11783IL_TIMExtendParametrizationRequest(dbNode client, byte functionId , byte controlMode, dword controlModeDataSize, byte controlModeData[]); // form 4`

## Description

The function extends a parameterization request by adding a control mode and its data to a parameterization request. The parameterization request can be sent to the TIM Server by [Iso11783IL_TIMSendParametrizationRequest](CAPLfunctionIso11783ILtimSendParametrizationRequest.md).

To remove the information added by this function you can call [Iso11783IL_TIMClearParametrizationRequest](CAPLfunctionIso11783ILtimClearParametrizationRequest.md).

## Parameters

- **functionId**: Function ID of the TIM function.
  - **Function ID**: Description
    - 1-32 (1h-20h): Auxiliary Value 1 – 32
    - 64 (40h): Front PTO
    - 65 (41h): Rear PTO
    - 66 (42h): Front hitch
    - 67 (43h): Rear hitch
    - 68 (44h): Vehicle speed
    - 70 (46h): External guidance
    - 71 (47h): Front top linkage
    - 72 (48h): Rear top linkage

- **controlMode**: Parameter request control mode.

- **controlModeDataSize**: Number of bytes of the additional data for the specified control mode.

- **controlModeData**: Additional data for the specified control mode.

- **client**: TIM client simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully.
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md).
- **-102**: Invalid address, invalid function ID or parameter **controlModeDataSize** is smaller than size of **controlModeData**.

## Example

See [Iso11783IL_TIMSendParametrizationRequest](CAPLfunctionIso11783ILtimSendParametrizationRequest.md)

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
