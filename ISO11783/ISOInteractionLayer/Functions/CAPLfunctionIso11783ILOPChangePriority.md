[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangePriority.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangePriority

# Iso11783IL_OPChangePriority

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangePriority( dword maskID, dword priority ); // form 1
long Iso11783IL_OPChangePriority( dbNode implement, dword maskID, dword priority ); // form 2
```

## Description

The function changes the priority of an alarm mask. A **Change Priority** command is sent to the Virtual Terminal.

## Parameters

- **maskID**: Object ID of an alarm mask
- **priority**: Priority of the alarm mask
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangePriority( 1200, 2 );
```
