[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCableCheckResDin.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Test Functions** » **Shared Functions** » **SCC_CreateCableCheckRes_DIN**

# SCC_CreateCableCheckRes_DIN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateCableCheckRes_DIN 
( byte SessionID[], char ResponseCode[], 
long NotificationMaxDelay, char StatusCode[], 
char Notification[], long EVSEProcessing )
```

## Description

Creates a Cable Check Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for DC_EVSEStatus).
- **StatusCode**: Internal state of the EVSE (for DC_EVSEStatus).
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for DC_EVSEStatus).
- **EVSEProcessing**: 0 if **Finished**, 1 if **Ongoing**, 2 if **Ongoing_WaitingForCustomerInteraction** (ISO 15118).

### Optional Parameters

- **Index**: 0
- **Name**: IsolationStatus
- **Type**: char[]
- **Description**: Current isolation condition.

## Return Values

- **0**: Else (message cannot be sent).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
