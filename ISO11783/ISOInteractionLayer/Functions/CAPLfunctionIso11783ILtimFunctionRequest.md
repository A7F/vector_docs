[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimFunctionRequest.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMFunctionRequest

# Iso11783IL_TIMFunctionRequest

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMFunctionRequest(byte functionId, word requestValue); // form 1`
- `long Iso11783IL_TIMFunctionRequest(byte functionId, word requestValue, long requestCounter); // form 2`
- `long Iso11783IL_TIMFunctionRequest(dbNode client, byte functionId, word requestValue); // form 3`
- `long Iso11783IL_TIMFunctionRequest(dbNode client, byte functionId, word requestValue, long requestCounter); // form 4`

## Description

The function sends a function request value to the TIM server to control a TIM function. The function fails if the TIM function is not assigned to the TIM client.

### TIM Starting With version 2

Starting with TIM version 2 no request counter is used in function request messages. Therefore, the parameter **requestCounter** is ignored.

By default, the request counter is set to **15** (request counter is not used). If the property **useRequestCounter** (see [Iso11783IL_TIMSetProperty](CAPLfunctionIso11783ILtimSetProperty.md)) is set to **1** then the counter is incremented each time the request value for this function is sent (up to value **13**, then start with **0** again). You can use form 2 to set the request counter directly. The function value request is sent with a maximum repetition rate of 100 ms even this CAPL function is called more frequently. The last request value is transmitted with repetition rate 2000 ms periodically if this function is not called.

## Parameters

- **functionID**: Function ID of the function.
  - 1-32 (1h-20h): Auxiliary Value 1 – 32, Supported Since TIM Version: 1
  - 64 (40h): Front PTO, Supported Since TIM Version: 1
  - 65 (41h): Rear PTO, Supported Since TIM Version: 1
  - 66 (42h): Front hitch, Supported Since TIM Version: 1
  - 67 (43h): Rear hitch, Supported Since TIM Version: 1
  - 68 (44h): Vehicle speed, Supported Since TIM Version: 1
  - 70 (46h): External guidance, Supported Since TIM Version: 1
  - 71 (47h): Front top linkage, Supported Since TIM Version: 2
  - 72 (48h): Rear top linkage, Supported Since TIM Version: 2

  Note: To set the supported TIM version, use the [Iso11783IL_TIMSetProperty](CAPLfunctionIso11783ILtimSetProperty.md) function with the **implementedVersion** property.

- **requestValue**: Requested raw value of the TIM function.

- **requestCounter**: Set the request counter to this value.
  - 0..13: Valid counter value
  - 15: Request counter is not used
  - -1: Automatically increment the last used request counter value. If the last used request counter value is 15 then the request counter is not changed

- **client**: TIM client simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
