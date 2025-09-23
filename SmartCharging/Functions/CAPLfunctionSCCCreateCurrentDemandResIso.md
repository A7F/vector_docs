[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCurrentDemandResIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateCurrentDemandRes_ISO**

# SCC_CreateCurrentDemandRes_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateCurrentDemandRes_ISO 
( byte SessionID[], char ResponseCode[], 
long NotificationMaxDelay, char StatusCode[], 
char Notification[], float PresentValues[], 
byte LimitAchievedFlags[], char EVSEID[], 
long SAScheduleTupleID )
```

## Description

Creates a Current Demand Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. See [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for DC_EVSEStatus).
- **StatusCode**: Internal state of the EVSE (for DC_EVSEStatus).
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for DC_EVSEStatus).
- **PresentValues**:
  - PresentValues [0] = EVSEPresentVoltage
  - PresentValues [1] = EVSEPresentCurrent
- **LimitAchievedFlags**:
  - LimitAchievedFlags [0] = EVSECurrentLimitAchieved
  - LimitAchievedFlags [1] = EVSEVoltageLimitAchieved
  - LimitAchievedFlags [2] = EVSEPowerLimitAchieved
- **EVSEID**: Unique ID of the charge point.
- **SAScheduleTupleID**: ID of the selected SAScheduleTuple.

### Optional Parameters

- **Index 0**: IsolationStatus (char[]) - Current isolation condition.
- **Index 1**: MaxVoltage (float) - EVSEMaximumVoltageLimit.
- **Index 2**: MaxCurrent (float) - EVSEMaximumCurrentLimit.
- **Index 3**: MaxPower (float) - EVSEMaximumPowerLimit.
- **Index 4**: ReceiptRequired (long) - Indicates if the vehicle is required to send a MeteringReceiptReq.
- **Index 5**: MeterID (char[]) - Unique ID of the meter.
- **Index 6**: MeterReading (dword) - Current meter reading in Wh.
- **Index 7**: SigMeterReading (byte[]) - Signature of the meter reading (length 64).
- **Index 8**: MeterStatus (long) - Current status of the meter.
- **Index 9**: TMeter (long) - Timestamp of the current SECC time.

**Note**: Due to the requirements of the schema, the element **MeterID** is mandatory if any of the optional meter-related parameters are to be supplied.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
