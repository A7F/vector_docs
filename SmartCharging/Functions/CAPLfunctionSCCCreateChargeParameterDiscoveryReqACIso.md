[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateChargeParameterDiscoveryReqACIso.md)

## SCC_CreateChargeParameterDiscoveryReqAC_ISO

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Test Functions** » **Shared Functions** » **SCC_CreateChargeParameterDiscoveryReqAC_ISO**

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long SCC_CreateChargeParameterDiscoveryReqAC_ISO 
( byte SessionID[], char EnergyTransferType[], 
float EAmount, float MaxVoltage, 
float MaxCurrent, float MinCurrent )
```

### Description

Creates a Charge Parameter Discovery Request message for sending, using the AC syntax.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **EnergyTransferType**: Desired charging mode.
- **EAmount**: Desired amount of energy in Wh.
- **MaxVoltage**: EVMaxVoltage
- **MaxCurrent**: EVMaxCurrent
- **MinCurrent**: EVMinCurrent

#### Optional Parameters

| Index | Name                   | Type  | Description                                         |
|-------|------------------------|-------|-----------------------------------------------------|
| 0     | MaxEntriesSAScheduleTuple | long  | Maximal number of entries in the SAScheduleTuple.   |
| 1     | DepartureTime          | dword | Intended time to finish the charging process, in "seconds from now". |

### Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

### Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
