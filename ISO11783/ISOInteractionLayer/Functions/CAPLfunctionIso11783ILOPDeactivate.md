[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPDeactivate.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPDeactivate

# Iso11783IL_OPDeactivate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPDeactivate(); // form 1
long Iso11783IL_OPDeactivate(dword options); // form 2
long Iso11783IL_OPDeactivate(dbNode implement, dword options); // form 3
```

## Description

The function terminates the connection to the Virtual Terminal.

The **Delete Object Pool** command is executed to log off from the Virtual Terminal. The **Maintenance** message is no longer sent. The Object Pool API changes to state **Not Active**.

## Parameters

- **options**: Options
  - bit 0 = 1: suppress **Delete Object Pool** command
  - bit 1 = 1: delete local object pool

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
