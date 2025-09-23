[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetOUI.md)

### SCC_SLAC_GetOUI

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetOUI

**Valid for**:  CANoe DE • CANoe4SW DE

#### Function Syntax

```plaintext
void SCC_SLAC_GetOUI(byte OUI[]);
```

#### Description

Gets the 3 byte OUI of a vendor specific message.

Currently supported OUIs:

- Qualcomm (0x00B052)
- MStar, MediaTek and Vertexcom (0x0013D7)
- Lumissil (0x0016E8)

#### Parameters

- **OUI**: Queries the vendor OUI of the chip (to the given byte buffer).

#### Return Values

—

#### Example

—
