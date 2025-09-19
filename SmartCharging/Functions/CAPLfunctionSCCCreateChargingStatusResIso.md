[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateChargingStatusResIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateChargingStatusRes_ISO**

# SCC_CreateChargingStatusRes_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateChargingStatusRes_ISO ( byte SessionID[], char ResponseCode[], long NotificationMaxDelay, byte StatusFlags[], char Notification[], char EVSEID[], long SAScheduleTupleId )
```

## Description

Creates a Charging Status Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for AC_EVSEStatus).
- **StatusFlags**: Flags for AC_EVSEStatus: StatusFlags[0] = PowerSwitchClosed, StatusFlags[1] = RCD.
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for AC_EVSEStatus).
- **EVSEID**: Unique ID of the charge point.  
  **Note**: EVSEID is interpreted as a 64 bit number, and thus must not contain any letters.
- **SAScheduleTupleId**: Unique ID of a SAScheduleTuple which identifies the selected Tariff.

### Optional Parameters

| Index | Name             | Type   | Description                                                |
|-------|------------------|--------|------------------------------------------------------------|
| 0     | MeterID          | char[] | Unique ID of the meter.                                    |
| 1     | MeterReading     | long   | Current meter reading in Wh.                               |
| 2     | SigMeterReading  | byte[] | Signature of the meter reading (length 64).                |
| 3     | MeterStatus      | long   | Current status of the meter.                               |
| 4     | TMeter           | long   | Timestamp of the current SECC time.                        |
| 5     | MaxCurrent       | float  | EVSEMaxCurrent.                                            |
| 6     | ReceiptRequired  | long   | Indicates if the vehicle is required to send a MeteringReceiptReq. |

**Note**: Due to the requirements of the schema, the element **MeterID** is mandatory if any of the optional meter-related parameters are to be supplied.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
