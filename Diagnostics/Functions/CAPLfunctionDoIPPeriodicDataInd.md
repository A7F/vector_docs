# _DoIP_PeriodicDataInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void _DoIP_PeriodicDataInd( byte buffer[], dword count, dword sourceAddress, dword targetAddress, byte timeBaseStatus, dword nanosecondsPartOfTime, dword secondsPartOfTime, dword remainingDataRecords);
```

## Description

This callback is called from the DoIP layer when periodic data according to ISO 13400-2:2019/Amd1 is received. Note that the callback may be called several times for one DoIP periodic response message PDU of payload type 0x8004, depending on how many periodic data identifiers are transmitted in the DoIP PDU.

## Parameters

- **buffer**: Buffer containing the received data.
- **count**: Size of the received data in bytes.
- **sourceAddress**: Logical DoIP address of the sender.
- **targetAddress**: Logical DoIP address of the receiver.
- **timeBaseStatus**: Synchronization state of the ECU local time base with the vehicle’s global time base.
- **nanosecondsPartOfTime**: Time stamp according ISO 13400-2:2019/Amd1.
- **secondsPartOfTime**: Time stamp according ISO 13400-2:2019/Amd1.
- **remainingDataRecords**: Expected further data records. Indicates the number of further calls of this callback for the currently processed DoIP PDU.

## Return Values

—

## Example

```c
void _DoIP_PeriodicDataInd( byte buffer[], dword count, dword sourceAddress, dword targetAddress, byte timeBaseStatus, dword nanosecondsPartOfTime, dword secondsPartOfTime, dword remainingDataRecords)
{
  write("Periodic data from source address 0x%x received, periodic data identifier is 0x%x", sourceAddress, buffer[0]);
}
```
