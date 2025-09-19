[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCMeteringReceiptReq.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EVSE Callback Functions** » **SCC_MeteringReceiptReq**

# SCC_MeteringReceiptReq

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_MeteringReceiptReq ( byte SessionID[], 
byte MessageSessionID[], 
long ScheduleTableEntryID )
```

## Description

The callback is called as soon as a Metering Receipt Request is received. With this request, the vehicle confirms receipt of the metering information sent by the charge point. Further details that are transmitted in this request can be queried with the helper function [SCC_GetMeterInfoData](../Functions/CAPLfunctionSCCGetMeterInfoData.md).

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **MessageSessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF, as transferred within the message body.
- **ScheduleTableEntryID**: ID of the selected SAScheduleTuple.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
