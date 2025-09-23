[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINActivateResps.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linActivateResps

# linActivateResps

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long linActivateResps(); // form 1`
- `long linActivateResps(char nodeName[]); // form 2`

## Description

Reactivates all frame responses published by the calling Slave node according to the LIN database file (LDF), after having been previously deactivated by [linDeactiveResps()](CAPLfunctionLINDeactivateResps.md) or [linResetSlave()](CAPLfunctionLINResetSlave.md).

Per default, all frame responses are activated for Slave nodes on measurement start, assuming Slave nodes have nonvolatile memory.

LIN2.0 Slave nodes will automatically activate responses for re-configurable frames on receiving valid reconfiguration commands, e.g., AssignFrameID.

Individual frame responses can be activated manually using the function [linSetRespCounter](CAPLfunctionLINSetRespCounter.md).

With form 2, you can activate the Slave responses of the selected Slave node (**nodeName**). If the parameter **nodeName** is not set or an empty string is given, the Slave responses of the node invoking this function will be deactivated.

**Note:** Form 2 has only an effect if the target is a program node that was assigned to a Slave node from the selected LIN database.

## Parameters

- **nodeName**: Slave node

## Return Values

Number of activated frame responses or -1 if an error occurs.

## Example

—

[linSetRespCounter](CAPLfunctionLINSetRespCounter.md) • [linDeactivateResps](CAPLfunctionLINDeactivateResps.md) • [linResetSlave](CAPLfunctionLINResetSlave.md)
