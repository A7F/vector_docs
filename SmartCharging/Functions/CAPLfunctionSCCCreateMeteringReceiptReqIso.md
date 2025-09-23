[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateMeteringReceiptReqIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateMeteringReceiptReq_ISO**

# SCC_CreateMeteringReceiptReq_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateMeteringReceiptReq_ISO ( byte SessionID[], long SAScheduleTupleId, char MeterID[], char ReceiptID[] )
```

## Description

Creates a Metering Receipt Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **SAScheduleTupleId**: Unique ID of a SAScheduleTuple which identifies the selected Tariff.
- **MeterID**: Unique ID of the meter.
- **ReceiptID**: Unique ID of the MeteringReceiptReq message.

### Optional Parameters

1. **MeterReading**: `long` - Current meter reading in Wh
2. **SigMeterReading**: `byte []` - Signature of the meter reading (length 64)
3. **MeterStatus**: `long` - Current status of the meter
4. **TMeter**: `long` - Timestamp of the current SECC time

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
