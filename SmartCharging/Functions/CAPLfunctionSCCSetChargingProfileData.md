[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetChargingProfileData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data (write)](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetChargingProfileData

# SCC_SetChargingProfileData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
long SCC_SetChargingProfileData(long Index, long Start, double MaxPower, long NumberOfPhases);
```

## Description

This function allows to dynamically adapt a pre-loaded ChargingProfile to the SASchedule previously received from an EVSE.

It overwrites the fields **ChargingProfileEntryStart**, **ChargingProfileEntryMaxPower** and/or **ChargingProfileEntryMaxNumberOfPhasesInUse** in a pre-loaded ChargingProfile of a PowerDeliveryReq (start) message. The ChargingProfile must have previously been loaded from the vehicle [XML-config](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md) by calling [SCC_SetOptionalParameterFromConfig](CAPLfunctionSCCSetOptionalParameterFromConfig.md).

An error will be returned if no profile has been loaded.

**Note**

- This function is only available in passive mode (EV messages are created by application code).
- This function does not create any missing optional fields or new entries.

## Parameters

- **Index**: The index of the **ProfileEntry** to be modified, starting at 0 (zero). An error will be returned if the index is invalid.
- **Start**: The new value for **ChargingProfileEntryStart**. No changes will be made if the value is \< 0.
- **MaxPower**: The new value for **ChargingProfileEntryMaxPower**. No changes will be made if the value is \< 0.
- **NumberOfPhases**: The new value for **ChargingProfileEntryMaxNumberOfPhasesInUse**. This optional field must already exist in the (XML) profile, it will not be created. No changes will be made if the value is \\\< 0.

## Return Values

- **0**: error
- **1**: success

## Example

**Example**

```plaintext
// create a PowerDeliveryReq message
SCC_CreatePowerDeliveryReqAC_ISO( SessionId, "Start", SAScheduleTupleId);
// add the ChargingProfile from the XML config section #10
SCC_SetOptionalParameterFromConfig(0, 10);
// modify only the MaxPower value of entry #1
SCC_SetChargingProfileData(1, -1, 3000.0, -1)
// send the modified message
SCC_SendPreparedMessage();
```

[SCC_CreatePowerDeliveryReqAC_ISO](CAPLfunctionSCCCreatePowerDeliveryReqACIso.md) • [SCC_CreatePowerDeliveryReqDC_ISO](CAPLfunctionSCCCreatePowerDeliveryReqDCIso.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
