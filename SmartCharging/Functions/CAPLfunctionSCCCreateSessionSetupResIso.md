[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateSessionSetupResIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateSessionSetupRes_ISO**

# SCC_CreateSessionSetupRes_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateSessionSetupRes_ISO 
( byte SessionID[], char ResponseCode[], 
char EVSEID[] )
```

## Description

Creates a Session Setup Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **EVSEID**: Unique ID of the charge point.

  **Note**: EVSEID is interpreted as a 64 bit number, and thus must not contain any letters.

- **Optional Parameters**:
  - **Index**: 0
  - **Name**: Timestamp
  - **Type**: long
  - **Description**: Timestamp of the current charge point time.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
