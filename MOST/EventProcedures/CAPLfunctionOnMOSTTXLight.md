[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTTXLight.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostTxLight

# OnMostTxLight

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note:** Only available with VN2600/VN2610!

## Function Syntax

```
OnMostTxLight(long mode);
```

## Description

The event procedure is called as soon as the light status of the fibre optical transmitter (FOT) is switched.

**Note:** The event procedure is only called if the light status has been switched by the application (see also [mostSetTxLight](../Functions/CAPLfunctionMOSTSetTxLight.md)).

## Parameters

- **mode**: Light status of the FOT:
  - `0`: FOT disabled: Tx light off
  - `1`: FOT enabled: TimingMaster: Modulated light on; TimingSlave/Bypass: Tx light = Rx light
  - `2`: FOT enabled: Constant light on

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)