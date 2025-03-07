[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPActivate.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPActivate

# Iso11783IL_OPActivate

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPActivate(); // form 1`
- `long Iso11783IL_OPActivate(dword options); // form 2`
- `long Iso11783IL_OPActivate(dbNode implement, dword options); // form 3`

## Description

The function activates the Object Pool API. The initialization procedure with the Virtual Terminal is performed and the object pool is transmitted to the Virtual Terminal.

During the initialization procedure some information from the Virtual Terminal is requested. This can be suppressed with the **options** parameter. The requested information can be get with the function [Iso11783IL_OPGetVTInfo](CAPLfunctionIso11783ILOPGetVTInfo.md).

**Note**: This function is not necessary if a node was configured completely in the database (DBC):  
**ISO11783IOPFilename** and **ISO11783IOPVersion** are defined and **VT21** message was assigned to the node.

## Parameters

- **options**: Options
  - bit 0 = 1: suppress **Get Memory** command
  - bit 1 = 1: suppress **Get Number of Softkeys** command
  - bit 2 = 1: suppress **Get Text Font Data** command
  - bit 3 = 1: suppress **Get Hardware** command

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example 1**

```plaintext
Iso11783IL_OPSetProperty("Version", 5);
Iso11783IL_OPLoad("ObjectPool.iop", "pool001");
Iso11783IL_OPActivate();
```

**Example 2**  
Move to another Virtual Terminal (VT)

```plaintext
void MoveToVtWithFunctionInstance1()
{
  Iso11783IL_OPDeactivate();
  Iso11783IL_OPSetProperty("VTFunctionInstance", 1);
  SetTimer(mMoveTimer, 1000);
}

on timer mMoveTimer
{
  Iso11783IL_OPLoad("Sprayer.iop");
  Iso11783IL_OPActivate();
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)