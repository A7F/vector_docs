[SCC_GetPMaxScheduleEntryCount](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetPMaxScheduleEntryCount.md)

# SCC_GetPMaxScheduleEntryCount

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Data Queries** » **EV Functions** » **SCC_GetPMaxScheduleEntryCount**

**Valid for**: CANoe DE • CANoe4SW DE

### Note
- This function applies only to the SAScheduleList of ISO 15118.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
long SCC_GetPMaxScheduleEntryCount ( long Index )
```

## Description

Gets the number of entries in the **PMaxSchedule**.

## Parameters

- **Index**: Selected index of a SAScheduleTuple.

## Return Values

Returns the number of **PMaxScheduleEntries** in the subelement **PMaxSchedule** of the **SAScheduleTuple** with the selected index.

## Example

—

[SCC_GetPMaxScheduleEntryData](CAPLfunctionSCCGetPMaxScheduleEntryData.md) • [SCC_GetPMaxScheduleID](CAPLfunctionSCCGetPMaxScheduleID.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)