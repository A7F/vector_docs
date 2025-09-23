[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimUnassignFunction.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_TIMUnassignFunction**

# Iso11783IL_TIMUnassignFunction

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMUnassignFunction(byte functionId); // form 1`
- `long Iso11783IL_TIMUnassignFunction(byte functionId, dword options); // form 2`
- `long Iso11783IL_TIMUnassignFunction(dbNode client, byte functionId); // form 3`
- `long Iso11783IL_TIMUnassignFunction(dbNode client, byte functionId, dword options); // form 4`

## Description

If the TIM client is already authenticated and enabled by the operator then the assignment process with the function to be released is started again. By using parameter option you can prevent starting the assignment process.

If the TIM function is not assigned this function removes the TIM function from the list of functions which shall be assigned to the TIM server.

To assign a TIM function you can use [Iso11783IL_TIMAssignFunction](CAPLfunctionIso11783ILtimAssignFunction.md).

## Parameters

- **function**: ID
  - Function ID of the function.
  - Function ID | Description | Supported Since TIM Version
    - 1-32 (1h-20h) | Auxiliary Value 1 – 32 | 1
    - 64 (40h) | Front PTO | 1
    - 65 (41h) | Rear PTO | 1
    - 66 (42h) | Front hitch | 1
    - 67 (43h) | Rear hitch | 1
    - 68 (44h) | Vehicle speed | 1
    - 70 (46h) | External guidance | 1
    - 71 (47h) | Front top linkage | 2
    - 72 (48h) | Rear top linkage | 2

  Note: To set the supported TIM version, use the [Iso11783IL_TIMSetProperty](CAPLfunctionIso11783ILtimSetProperty.md) function with the **implementedVersion** property.

- **options**: Additional options.
  - Option | Value | Description
    - Prevent assignment request | 01h | If the TIM client/server connection is already enabled by the operator the **TIM_FunctionsAssignmentRequest** is not sent at once.

- **client**: TIM client simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
