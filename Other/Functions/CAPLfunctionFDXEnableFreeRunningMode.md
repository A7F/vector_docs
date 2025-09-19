[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFDXEnableFreeRunningMode.md)

**CAPL Functions** » **General** » **Function Overview** » **FDXEnableFreeRunningMode**

# FDXEnableFreeRunningMode

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long FDXEnableFreeRunningMode(long fdxClientHandle, word groupID, word flags, dword cycleTime, dowrd firstDuration);
```

## Description

This function activates the **Free Running** mode for the specified FDX client. The behavior of the function corresponds to the reception of a **FreeRunningRequest** command via the [FDX protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocol.md).

You can find further information about the **Free Running** mode in the manual [CANoe_FDX_Protocol_EN.pdf](javascript:startDemoLoader('CANoe_FDX_Protocol_EN.pdf')).

## Parameters

- **fdxClientHandle**: FDX client for which the **Free Running** mode should be activated.
- **groupID**: Identifies the data group inside the FDX description file.
- **flags**: The flags describe when the data group will be transmitted.
  - 1: Transmits data group at pre start phase of the CANoe measurement
  - 2: Transmits data group at stop of measurement
  - 4: Transmits the data group cyclically while the measurement is running. The transmit cycle is defined by the fields **cycleTime** and **firstDuration**.
  - 8: Transmits the data group if the function [FDXTriggerDataGroup](CAPLfunctionFDXTriggerDataGroup.md) is called.
- **cycleTime**: Time period in nanoseconds for the free running mode.
- **firstDuration**: Time interval in nanoseconds for the first transmit cycle.

## Return Values

- **0**: Successful function call
- **-1**: The parameter **fdxClientHandle** is invalid.

## Example

[Coupling of two CANoe Instances using the FDX Protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocolCouplingCANoeInstances.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
