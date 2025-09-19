# on a429worderror

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Description

The event procedure `on a429worderror` is called on every event, related to an ARINC word error. The error type is available in the selector [error](../CAPLfunctionsA429Selectors.md#A429SelectorError).

Note that there are errors without any valid label information. This is especially the gap violation error. The ARINC word causing that error triggers a `on a429word` procedure. For this reason it makes sense to catch all errors in a single channel related handler.

ARINC word errors are also monitored with [statistics system variables](../../../CANoeCANalyzer/A429/windows/a429BusStatisticsWindow.md).

## Selectors

- **a429word**: More information about [a429word](../CAPLfunctionsA429DefineARINCword.md).

## Example

| Example                          | Triggering ARINC word error event         |
|----------------------------------|-------------------------------------------|
| on a429worderror *| error with any label                      |
| on a429worderror MsgChannel7.*   | error with any label on channel 7         |

- A429 CAPL Functions
- [a429CalcBitLength](../Functions/CAPLfunctionA429CalcBitLength.md#aanchor32119)
- [a429CheckParity](../Functions/CAPLfunctionA429CheckParity.md#aanchor28518)
- [a429GetBitLength](../Functions/CAPLfunctionA429GetBitLength.md#aanchor26856)
- [a429GetConfiguration](../Functions/CAPLfunctionA429GetConfiguration.md#aanchor24055)
- [a429GetErrorPosition](../Functions/CAPLfunctionA429GetErrorPosition.md#aanchor1775)
- [a429ResetEx](../Functions/CAPLfunctionA429ResetEx.md#aanchor30313)
- [a429SetConfiguration](../Functions/CAPLfunctionA429SetConfiguration.md#aanchor28708)
- [a429SetGap](../Functions/CAPLfunctionA429SetGap.md#aanchor5098)
- [a429SetParity](../Functions/CAPLfunctionA429SetParity.md#aanchor19802)
- [a429SetScheduleTx](../Functions/CAPLfunctionA429SetScheduleTx.md#aanchor9654)
- [a429StopTx](../Functions/CAPLfunctionA429StopTx.md#aanchor20252)
- [a429Transmit](../Functions/CAPLfunctionA429Transmit.md#aanchor29809)
- [ARINC Word Selectors](../CAPLfunctionsA429Selectors.md#aanchor11110)
- [Declaration of ARINC Words (A429)](../CAPLfunctionsA429DefineARINCword.md#aanchor5265)
- [on a429error](CAPLfunctionA429OnA429Error.md#aanchor8408)
- [on a429word](CAPLfunctionA429OnA429Word.md#aanchor19756)
- [on a429worderror](#aanchor12007)
- [output (A429)](../Functions/CAPLfunctionA429output.md#aanchor10655)
- [Reconfigure a Channel (A429)](../CAPLfunctionsA429ChannelReconfig.md#aanchor870)
- [Scheduling an ARINC Word (A429)](../CAPLfunctionsA429Scheduling.md#aanchor1455)
