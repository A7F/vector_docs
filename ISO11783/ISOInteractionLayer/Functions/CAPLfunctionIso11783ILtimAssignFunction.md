[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimAssignFunction.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMAssignFunction

# Iso11783IL_TIMAssignFunction

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
A TIM Client simulated with the ISO1183 IL does not store a TIM system configuration. Functions have to be assigned with `Iso11783IL_TIMAssignFunction`.

## Function Syntax

- `long Iso11783IL_TIMAssignFunction(byte functionId, dbNode server); // form 1`
- `long Iso11783IL_TIMAssignFunction(byte functionId, dbNode server, dword options); // form 2`
- `long Iso11783IL_TIMAssignFunction(byte functionId, byte serverAddress); // form 3`
- `long Iso11783IL_TIMAssignFunction(byte functionId, byte serverAddress, dword options); // form 4`
- `long Iso11783IL_TIMAssignFunction(dbNode client, byte functionId, dbNode server); // form 5`
- `long Iso11783IL_TIMAssignFunction(dbNode client, byte functionId, dbNode server, dword options); // form 6`
- `long Iso11783IL_TIMAssignFunction(dbNode client, byte functionId, byte serverAddress); // form 7`
- `long Iso11783IL_TIMAssignFunction(dbNode client, byte functionId, byte serverAddress, dword options); // form 8`

## Description

The function assigns a TIM function of the TIM client to a TIM server.

After receiving the **TIM_FunctionsSupportResponse** message of the server the client checks if:

a) the TIM function facilities added by this [Iso11783IL_TIMSetRequiredFacility](CAPLfunctionIso11783ILtimSetRequiredFacility.md) AND  
b) the TIM functions assigned by this CAPL function

are supported by the server.

After the TIM client is successfully authenticated and enabled by the operator, it starts the assignment process for all TIM functions which are configured by this CAPL function.

If the TIM client is already authenticated and enabled by the operator then the assignment process with the additional function ID to be assigned is started again. By using parameter option you can prevent starting the assignment process.

To release an assigned TIM function you can use **Iso11783IL_TIMUnassingFunction**.

## Parameters

- **functionID**  
  Function ID of the TIM function.

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

- **server**  
  The TIM client starts the function assignment procedure for the TIM function to the TIM server specified by this parameter.

- **serverAddress**  
  The TIM client starts the function assignment procedure for the TIM function to the TIM server which uses this address. Value range: 0..253.

- **options**  
  Additional options.

  - Prevent assignment request: 01h  
    If the TIM client/server connection is already enabled by the operator the TIM_FunctionsAssignmentRequest is not sent at once.

- **client**  
  TIM client simulation node to apply the function.

## Return Values

- **0**  
  Property has been set successfully

- **< 0**  
  An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—