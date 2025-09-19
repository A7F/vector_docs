[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetMeterInfoData.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Data Queries** » **Shared Functions** » **SCC_GetMeterInfoData**

# SCC_GetMeterInfoData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Note

- This function can be called only within the assigned callback. The function is used to query the details of a request or of a SLAC or V2G message.
- This function is available for the messages **ChargingStatusRes**, **CurrentDemandRes** and **MeteringReceiptRes** if a MeterInfo element is contained.
- This function is only available using ISO protocol.
- `<InvalidValueSigned>` and / or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetMeterInfoData ( char MeterID[], dword& MeterReading, byte SigMeterReading[], long& MeterStatus, long& TMeter )
```

## Description

Gets data from MeterInfo.

## Parameters

- **MeterID**: Queries the MeterId as string with 32 characters (to the given char buffer).
- **MeterReading**: Gets the current meter reading in [Wh] (via reference).
- **SigMeterReading**: Queries the signature of meter reading (to the given byte buffer). The length depends on the encryption algorithm. 64-byte long array of zeros if the value is not available.
- **MeterStatus**: Gets the meter status (via reference).
- **TMeter**: Gets the timestamp in UNIX format (via reference).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
