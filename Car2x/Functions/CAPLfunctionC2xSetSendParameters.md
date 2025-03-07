[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetSendParameters.md)

**CAPL Functions » Car2x » C2xSetSendParameters**

# C2xSetSendParameters

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

`C2xSetSendParameters(LONG appChannel, LONG txPower, LONG antenna, LONG dataRate, LONG expiry)`

## Description

Set transmission relevant send parameters.

This method allows to redefine some or all transmission related parameters on the fly; for all following transmissions on a specific VN4610 channel those new default values will be used.

In fact the method overwrites the corresponding internal configuration settings provided by the setup-dialog.

To set just a subset of the parameters the value `<-1>` can be used for antenna, dataRate and expiry to leave the corresponding parameters of the configuration unchanged.

**Note**: This method can only be used with VN4610 hardware.

## Parameters

- **appChannel**: Channel to apply settings to (1 .. n), n = available hardware channels (1=Ath1, 2=Ath2,…)
- **txPower**: Transmission power in dBm; use **-100** to keep the original setting.
- **antenna**: Antenna used for Tx:
  - 1: Ant1
  - 2: Ant2
  - 3: both
  - -1: keep the original setting
- **dataRate**: Data rate [Mbps] to be used (use **4** to set 4.5Mbps);
  - Allowed values: 3,4,6,9,12,18,24,27
  - -1: keep the original setting
- **expiry**: MAC expiry time [µs]
  - 0: never
  - -1: keep the original setting

## Return Values

- **0**: Success
- **≠0**: Error code as in [C2xConfigureChannel](CAPLfunctionC2xConfigureChannel.md).

## Example

```plaintext
on key '1'
{
  Write("Set SendParameters for Ch1 to 10dBm  Ant2, 9Mbps; don’t change expiry ");
  C2xSetSendParameters(1, 10, 2, 9, -1);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)