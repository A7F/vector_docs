[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPConnectSysVar.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPConnectSysVar

# Iso11783IL_OPConnectSysVar

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPConnectSysVar( dword objectId, char sysVarNameWithPath[] ); // form 1
long Iso11783IL_OPConnectSysVar( dbNode implement, dword objectId, char sysVarNameWithPath[] ); // form 2
```

## Description

Connects an object from the object pool (on implement side) to a system variable. Only the following objects are supported:

- **Input Object**
  - Input Boolean
  - Input Number
  - Input List
  - Input String

- **Output Object**
  - Output Number
  - Output List
  - Output Meter
  - Output Linear Bar Graph
  - Output Arched Bar Graph
  - Output String

- **Input/Output Object**
  - Number Variable
  - String Variable

The connected system variable receives the value that was sent by the Virtual Terminal to the ECU via VT Change Numeric Value Message or VT Change String Value Message and modified the object value in the object pool on the implement side.

If the system variable in CANoe DE product itself is modified (e.g., in CAPL or in a panel), the object value in the object pool on the implement side is modified and sent to the Virtual Terminal with the **Change Numeric Value** or **Change String Value** command.

To release connection between the system variable and an object from the object pool, just call the same method again, but with the empty string instead of the name of system variable.

## Parameters

- **objectId**: Identifier of the object in the object pool
- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
int ret;
ret = Iso11783IL_OPConnectSysVar(10100, "ConnectedSysVars::svIntVar"); // connect
...
ret = Iso11783IL_OPConnectSysVar(10100, ""); // release
```
