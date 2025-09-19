[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetChargingProfileDataDynamically.md)

## SCC_SetChargingProfileDataDynamically

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Simulation Data (write)** » **EV Functions** » SCC_SetChargingProfileDataDynamically

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long SCC_SetChargingProfileDataDynamically(byte SessionID[], long SelectedTupleID);
```

### Description

This function allows to dynamically create a ChargingProfile matching the SASchedule previously received from an EVSE. The profile will be added to the created message automatically.

### Parameters

- **SessionID**: The SessionID of the ChargeParameterDiscovery.Res message that provides the SAScheduleList from which the ChargingProfile is to be derived.
- **SelectedTupleID**: Tuple that should be used as a basis for the created ChargingProfile.

### Return Values

- **0**: error
- **1**: success

### Example

```plaintext
// create a PowerDeliveryReq message
SCC_CreatePowerDeliveryReqAC_ISO( SessionId, "Start", 1);
// create a ChargingProfile matching the SAScheduleTuple with ID 1
SCC_SetChargingProfileDataDynamically(SessionId, 1);
// send the modified message
SCC_SendPreparedMessage();
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
