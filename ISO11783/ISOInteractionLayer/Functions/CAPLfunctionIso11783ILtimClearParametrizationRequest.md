[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimClearParametrizationRequest.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMClearParametrizationRequest

# Iso11783IL_TIMClearParametrizationRequest

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMClearParametrizationRequest(byte functionId); // form 1`
- `long Iso11783IL_TIMClearParametrizationRequest(dbNode client, byte functionId); // form 2`

## Description

The function removes all information added by [Iso11783IL_TIMExtendParametrizationRequests](CAPLfunctionIso11783ILtimExtendParametrizationRequest.md) to a parameterization request.

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

- **client**: TIM client simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

See [Iso11783IL_TIMSendParametrizationRequest](CAPLfunctionIso11783ILtimSendParametrizationRequest.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)