[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFDXDisableFreeRunningMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » FDXDisableFreeRunningMode

# FDXDisableFreeRunningMode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long FDXDisableFreeRunningMode(long fdxClientHandle, word groupID);
```

## Description

This function disables the **Free Running** mode for the specified FDX client. The behavior of the function corresponds to the reception of a **FreeRunningCancel** command via the [FDX protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocol.md).

You can find further information about the **Free Running** mode in the manual [CANoe_FDX_Protocol_EN.pdf](javascript:startDemoLoader('CANoe_FDX_Protocol_EN.pdf')).

## Parameters

- **fdxClientHandle**: FDX Client for which the **FreeRunningMode** should be activated.
- **groupID**: Identifies the data group inside the FDX description file.

## Return Values

- **0**: Successful function call
- **-1**: The parameter **fdxClientHandle** is invalid.

## Example

[Coupling of two CANoe Instances using the FDX Protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocolCouplingCANoeInstances.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
