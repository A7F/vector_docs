[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetCorrectStartupSBC.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetCorrectStartupSBC

# mostSetCorrectStartupSBC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available for VN2600/VN2610.

## Function Syntax

```plaintext
long mostSetCorrectStartupSBC (long channel, long mode);
```

## Description

During the next start-up phase of the ring, this function activates or deactivates the correct setting of the "Synchronous Bandwidth Control" register (SBC) in the MOST chip (e.g. at the next wake-up of the ring).

**Note**

- This function has only an effect if the connected VN2600/VN2610 is configured as Timing Master.
- This function should only be executed if the connected VN2600/VN2610 is not in the start-up phase.

## Parameters

- **channel**: Channel of the connected MOST interface.
- **mode**:
  - `0`: inactive
  - `1`: active

## Return Values

—

## Example

—

[mostSetTimingMode](CAPLfunctionMOSTSetTimingMode.md) • [mostWakeup](CAPLfunctionMOSTWakeup.md) • [mostSetSBC](CAPLfunctionMOSTSetSBC.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
