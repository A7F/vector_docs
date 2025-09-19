[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDeactivateResps.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linDeactivateResps

# linDeactivateResps

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long linDeactivateResps(); // form 1
long linDeactivateResps(char nodeName[]); // form 2
```

## Description

This function deactivates frame responses for all frames published by the calling Slave node. The frame responses can be deactivated individually using the function [linSetRespCounter()](CAPLfunctionLINSetRespCounter.md).

With form 2 you can deactivate the Slave responses of the selected Slave node **(nodeName)**. If the parameter **nodeName** is not set or an empty string is given, the Slave responses of the node invoking this function will be deactivated.

**Note**

- If the CAPL-program calling this function, does not model a Slave node, then this function will have no effect.
- Form 2 has only an effect if the target is a program node that was assigned to a Slave node from the selected LIN database.
- If the **configurable_frames** list for the targeted Slave node is not complete, the function will not work correctly.

## Parameters

- **nodeName**: Slave node

## Return Values

Number of deactivated frame responses or -1 on failure.

## Example

—

[linSetRespCounter](CAPLfunctionLINSetRespCounter.md) • [linActivateResps](CAPLfunctionLINActivateResps.md) • [linResetSlave](CAPLfunctionLINResetSlave.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
