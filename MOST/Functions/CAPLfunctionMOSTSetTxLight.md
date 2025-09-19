[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetTxLight.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetTxLight

# mostSetTxLight

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**

This functionality is available for:

- VN2600/VN2610/VN2640
- OptoLyzerOL3150o (firmware version >= V1.5.3)

## Function Syntax

`long mostSetTxLight(long channel, long txlight);`

## Description

Sets the Light Status at the Fiber Optical Transmitter (FOT).

## Parameters

- **channel**: Channel of the interface to be queried
- **txlight**:
  - `0`: disable FOT: Tx light off
  - `1`: enable FOT:  
    - TimingMaster: Modulated light on
    - TimingSlave/Bypass: Tx light = Rx light
  - `2`: enable FOT: Constant light on (only available for VN2600/VN2610/VN2640/OptoLyzerOL3150o)
    - For OptoLyzerOL3150o: The stress network interface controller (NIC) must have its bypass opened (see [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)).

## Return Values

- `<0`: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetRxLight](CAPLfunctionMOSTGetRxLight.md) • [mostGetTxLight](CAPLfunctionMOSTGetTxLight.md) • [mostSetTxLightPower](CAPLfunctionMOSTSetTxLightPower.md) • [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [OnMostTxLight](../EventProcedures/CAPLfunctionOnMOSTTXLight.md) • [mostShutDown](CAPLfunctionMOSTShutDown.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
