[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSyncAlloc.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSyncAlloc

# mostSyncAlloc

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostSyncAlloc(long numChannels);
Callback: void OnMostSyncAllocResult(long allocResult, long numChannels, long channels[]);
```

## Description

**MOST25:**

This function reserves synchronous bandwidth by sending an Alloc system message to the MOST TimingMaster.

The result is reported by means of the callback function `OnMostSyncAllocResult()`. This requires defining `OnMostSyncAllocResult()` in the CAPL program using the following signature: `OnMostSyncAllocResult(long allocResult, long numChannels, long channels[])`

**Note**: The service can only process one request at a time. After `mostSyncAlloc()` or [mostSyncDealloc()](CAPLfunctionMOSTSyncDealloc.md) is called, the next request cannot be made until the result of the current request is returned – asynchronously.

**MOST150:**

Allocates synchronous bandwidth on MOST150.

**Note**:

- The callback function `OnMostSyncAllocResult` (see below) will not be called on completion. [mostAllocTableGetCL](CAPLfunctionMOSTAllocTableGetCL.md) can be applied to check the allocation result.
- Channels will be allocated only (e.g. for resource shortage tests). It is not possible to put any data on these channels.
- Specific for VN2640:
  - The bypass of the network interface controller (NIC) has to be open (see [mostSetAllBypass](CAPLfunctionMOSTSetAllBypass.md)).
  - At most ten labels can be allocated at a time.
- Specific for OptoLyzerOL3150o:
  - The bypass of the OptoLyzerOL3150o’s stress NIC has to be open (see [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)).

**Callback:**

This function is called on completion of the allocation of channels triggered by the call of the function.

Whether the allocation was successful and if so, which channels were allocated, is indicated in the parameters described below.

## Parameters

- **numChannels**: The number of channels to be reserved:
  - MOST25: 1 \<\= numChannels \<\= 8
  - MOST150: 1 \<\= numChannels \<\= MaxSyncBandwidth (depends on boundary settings - max. value: 372)

- **allocResult**: Result of the operation.
  - `kGrant = 0x01`: The channels were reserved
  - `kBusy = 0x02`: The channels were not reserved, because the TimingMaster is busy processing another request
  - `kDeny = 0x03`: The channels were not reserved, because there are no more channels available
  - `kWrong = 0x04`: The reservation request contains invalid parameters
  - `kUnknown = 0xFF`: Unspecified error (e.g. a timeout while waiting for the TimingMaster to respond)

- **numChannels**: The number of reserved channels. (1 \<\= numChannels \<\= 8).

- **channels[]**: The values contained in this parameter are valid for allocResult \= 0x01 only. It passes numChannels channel numbers reserved via `mostSyncAlloc()`. The value in channels[0] designates the label used for administration of the reserved channels.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[OnMostAllocTable](../EventProcedures/CAPLfunctionOnMOSTAllocTable.md) • [mostSyncDealloc](CAPLfunctionMOSTSyncDealloc.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md) • [mostSetSBC](CAPLfunctionMOSTSetSBC.md)
