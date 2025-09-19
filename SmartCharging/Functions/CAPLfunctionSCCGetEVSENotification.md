[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetEVSENotification.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **2G Data Queries** » **EV Functions** » **SCC_GetEVSENotification**

# SCC_GetEVSENotification

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetEVSENotification ( char EVSENotification[], long& NotificationMaxDelay  )
```

## Description

Gets the EVSENotification and its maximum delay, if present, from the EVSE status.

## Parameters

- **EVSENotification**: Queries the Notification of EVSE from DC_EVSEStatus (to the given char buffer).
- **NotificationMaxDelay**: Gets the maximum delay, if present, from DC_EVSEStatus (via reference).

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
