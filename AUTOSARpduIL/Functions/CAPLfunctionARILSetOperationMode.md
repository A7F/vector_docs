# ARILSetOperationMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- Please find the state graph that is traversed by these functions in [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md).
- Please note, that send panels require a running IL, otherwise the sending of PDUs cannot be controlled there.
- This function should not be used in the **on PreStart** event procedure.

## Function Syntax

```plaintext
long ARILSetOperationMode (long mode, long param); // form 1
long ARILSetOperationMode (dbSignal, long mode, long param); // form 2
long ARILSetOperationMode (dbMsg dbMessage, char signalGroupName[], long mode, long param); // form 3
```

## Description

Influences the behavior of the update bits and counters. The function without a signal or a signal group parameter has potentially impact on all possible signals and signal groups.

Influences the sending behavior of multiplexed I-PDUs. For each multiplexed I-PDU, which is specified in the database, the IL automatically creates two schedule tables. The first schedule table defines a sending pattern, which is based on the timings of the Sub I-PDUs from the database. Thus cannot be modified. The second schedule table is created with a default number of empty slots and can be modified by IL functions. Each slot can be assigned a multiplexer selector value or be marked as empty (no PDU transmission in this slot). If a schedule table is active, the PDU will be sent according to it.

## Parameters

- **dbSignal**: The symbolic name of an (UB/Mux) signal in the database.
- **dbMessage**: The symbolic name of a PDU in the database.
- **signalGroupName**: The symbolic full name of the signal group.
- **mode**: Defines which mode is to be influenced.
- **param**: Defines how a specific mode is to be interpreted:

  - **Mode 0, Parameter 0**: Enables the **Normal/Real** mode for UBs. Signals follow the **on update** semantic for setting the UB. After transmission of the PDU its UBs are reset. This is the default for this mode.
  - **Mode 0, Parameter 1**: Enables the **Plug&Play** mode for UBs. Thus, the UBs are always set.
  - **Mode 1, Parameter 0**: Enables the **Normal/Real** mode only for UBs of signal groups that have a counter. Signals follow the **on update** semantic for setting the UB. After transmission of the PDU its UBs are reset. This is the default for this mode.
  - **Mode 1, Parameter 1**: Enables the **Plug&Play** mode only for UBs of signal groups that have a counter. Thus, those UBs are always set.
  - **Mode 2, Parameter 0**: The specified signal or all signals of the specified PDU will not be able to awake the bus. (**NWM-WakeupAllowed** is set to **false**).
  - **Mode 2, Parameter 1**: The specified signal or all signals of the specified PDU will possibly awake the bus on changing its value. (**NWM-WakeupAllowed** is set to **true**).
  - **Mode 16, Parameter 0**: Disables scheduling for a specific multiplexed I-PDU. (form 2)
  - **Mode 16, Parameter 1**: Enables scheduling for a specific multiplexed I-PDU. Schedule table created from database timings is used. (form 2)
  - **Mode 16, Parameter 2**: Enables scheduling for a specific multiplexed I-PDU. User-defined schedule table is used. (form 2)
  - **Mode 17, Parameter 0**: Disables scheduling for all multiplexed I-PDUs. (form 1)
  - **Mode 17, Parameter 1**: Enables scheduling for all multiplexed I-PDUs. Schedule table created from database timings is used. (form 1)
  - **Mode 18, Parameter**: Number of slots (default: 50). Resizes the user-defined schedule table for a specific multiplexed I-PDU with the passed number. (form 2)
  - **Mode 19, Parameter 0**: Clears/Removes all multiplexer selector values from the user-defined schedule table of a specific multiplexed I-PDU. (form 2)
  - **Mode 20, Parameter**: Mux selector value. Adds a multiplexer selector value (param) at the next free slot of the user-defined schedule table for a specific multiplexed I-PDU. (form 2)
  - **Mode 21, Parameter**: Slot number (0…n). Marks a slot in the user-defined schedule table of the multiplexed I-PDU as empty slot. Thus no PDU will be sent in this slot. (form 2)
  - **Mode 200, Parameter**: `<OEM specific ID>`. Activates an OEM-specific E2E calculation. For affected OEMs, you will find the corresponding documentation in the OEM-specific help. To activate the OEM-specific calculation, the `SetOperationMode` function must be called in **on preStart** as first function. Available with CANoe DE product starting with version 15.
  - **Mode 2000, Parameter 0**: For signal groups with UB and SQC: The SQC and UB are triggered by signal updates. Changing the SQC will also trigger the UB. Signals follow the **on update** semantic for triggering the UB and SQC. SQC follows the **on change** semantic for triggering the UB.
    - The SQC may have impact on the UB.
    - The UB has not any impact on the SQC
  - **Mode 2000, Parameter 1**: For signal groups with UB and SQC: The SQC is always incremented before sending regardless of the signal group UB. Signals follow the **on update** semantic for triggering the UB.
    - The UB has not any impact on the SQC.
    - The SQC has not any impact on the UB.
    - This is the default for this mode.
  - **Mode 2000, Parameter 2**: For signal groups with UB and SQC: The SQC will only be incremented when the update bit is set. If the UB is **1** before transmission, then the SQC will be incremented once (for this transmission). Signals follow the **on update** semantic for triggering the UB.
    - An UB disturbance lets increment the SQC as long as the disturbance sets the UB.
    - The UB has impact on the SQC.
    - The SQC has not any impact on the UB.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—
