[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSyncDealloc.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSyncDealloc

# mostSyncDealloc

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostSyncDealloc(long label);
```

**Callback**: `void OnMostSyncDeallocResult(long deallocResult, long label);`

## Description

**MOST25:**

This function releases reserved bandwidth for synchronous channels by sending a Dealloc system message to the TimingMaster.

The result is reported by means of the callback function `OnMostSyncDeallocResult`. This requires defining `OnMostSyncDeallocResult` in the CAPL program using the following signature: `OnMostSyncDeallocResult(long deallocResult, long label)`

**Note**

- The service can only process one request at a time. After [mostSyncAlloc](CAPLfunctionMOSTSyncAlloc.md) or `mostSyncDealloc` is called, the next request cannot be made until the result of the current request is returned – asynchronously.
- `OnMostSyncDeallocResult()` is only called for channel labels reserved via [mostSyncAlloc](CAPLfunctionMOSTSyncAlloc.md).
- `OnMostSyncDeallocResult()` is also called for each reserved label if release of all channels is requested (DeallocAll).

**Most150:**

Deallocates synchronous bandwidth on MOST150.

**Note**

In contrast to MOST25, the callback function `OnMostSyncDeallocResult` will not be called on completion. [mostAllocTableGetCL](CAPLfunctionMOSTAllocTableGetCL.md) can be applied to check the de-allocation result.

**Callback:**

This function is called on completion of the deallocation of channels triggered by the call of the function.

Whether the deallocation was successful and if so, which channels were deallocated, is indicated in the parameters described below.

## Parameters

- **label**: Channel label.
  - **MOST25**: content of channels[0] in [OnMostSyncAllocResult](CAPLfunctionMOSTSyncAlloc.md), see [mostSyncAlloc](CAPLfunctionMOSTSyncAlloc.md). Value 0x7F (=DeallocAll) releases all synchronous channels.
  - **MOST150**: Label number (see [mostAllocTableGetCL](CAPLfunctionMOSTAllocTableGetCL.md)). Value 0xFFF releases all synchronous channels previously reserved with [mostSyncAlloc](CAPLfunctionMOSTSyncAlloc.md) (VN2640 only).

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[OnMostAllocTable](../EventProcedures/CAPLfunctionOnMOSTAllocTable.md) • [mostSyncAlloc](CAPLfunctionMOSTSyncAlloc.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md) • [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
