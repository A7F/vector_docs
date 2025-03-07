[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILNodeResetPDUTimingEvent.md)

**CAPL Functions** » **CANoe IL** » **ILNodeResetPDUTimingEvent**

# ILNodeResetPDUTimingEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note

- This function is only supported if the following components are used:
  - AUTOSAR PDU Interaction Layer (AsrPDUIL.dll) at the corresponding transmit node in the Simulation Setup.
  - AUTOSAR ≥ 4.2 database.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeResetPDUTimingEvent (dbMsg dbMessage, long TrueOrFalse)
```

## Description

Resets the event-timing to the values from the database. Possibly two timings (**False** and **True**) exist in parallel and are selected upon the current transmission mode of the PDU.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **TrueOrFalse**:
  - 0: denotes the **False** timing
  - 1: denotes the **True** timing
  - 3: denotes the **True** and the **False** timing

## Return Values

- **0**: No error
- **-10000**: Unspecific error
- **-10001**: Node or module not found
- **-10002**: No suitable module available
- **-10003**: Function is not supported by module
- **-10004**: Module returns illegal value
- **other**: Error in module

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)