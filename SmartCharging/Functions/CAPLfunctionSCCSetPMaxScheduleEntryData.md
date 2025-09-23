[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetPMaxScheduleEntryData.md)

## SCC_SetPMaxScheduleEntryData

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetPMaxScheduleEntryData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_SetPMaxScheduleEntryData(long i1, long i2, long Start, long Duration, float PMax);
```

### Description

Overwrites the **start**, **duration** and **PMax** values of the **PMaxScheduleEntry** at the given indices. The modified **SAScheduleList** will be sent with the next **ChargeParameterDiscovery** response.

**Note:**

- This function applies only to the SAScheduleList of ISO 15118.
- This function is used to programmatically modify a PMaxScheduleEntry of an SAScheduleList previously loaded from the [charge point XML configuration](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).
- It does not create any entries.

### Parameters

- **i1**: The index of the SAScheduleTuple, starting at 0 (zero). An error will be returned if no SAScheduleTuple exists at the given index.
- **i2**: The index of the PMaxScheduleEntry in the selected SAScheduleTuple to be modified, starting at 0. An error will be returned if no PMaxScheduleEntry exists at the given index.
- **Start**: The new start time within the RelativeTimeInterval field of the PMaxScheduleEntry.
- **Duration**: The new duration within the RelativeTimeInterval field of the PMaxScheduleEntry. Set this to -1 to omit the duration. An error will be returned if the field does not exist in the currently loaded SAScheduleList.
- **PMax**: The new Pmax value. Please note that the "Multiplier" is kept unchanged.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

```plaintext
// load EVSEConfiguration with ID="42"
SCC_LoadV2GConfig(42);
// set start time to 3000 and PMax to 0 in the second PMaxScheduleEntry of the first SAScheduleTuple
SCC_SetPMaxScheduleEntryData(0, 1, 3000, -1, 0);
```
