# A664SetStringSignal

**CAPL Functions** » **AFDX »** A664SetStringSignal

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

1. `long A664SetStringSignal (dbSignal aSignal, char val[])`
2. `long A664SetStringSignal (dbSignal aSignal, char val[], a664Message aMessage)`

## Description

This function can be used to set a string-signal within a specific a664Message (form 2) or to set the Tx-signal of the CANoe DE product subsystem (form 1).

For AFDX the usual string format contains the string length information at the first 2 bytes of the signal position, so the usual string operations won’t work correctly on string signals.

**Note**: To set opaque-type signals use the generic function [SetRawSignal](../../Test/Functions/CAPLfunctionSetRawSignal.md).

## Parameters

- **dbSignal**: The signal.
- **val**: The string to be used.
- **aMessage**: The message object where the signal value should be set for variant 2.

## Return Values

- **≥0**: Success. Number of characters applied. Oversized strings are automatically truncated to signal length.
- **-1**: Error.

## Example

```plaintext
a664Message TESTMSG_ALLTYPES testMsg = { msgChannel = 1};
a664SetStringSignal(TEST_STRING14_CITY, "STR126"); // set signal value on signalServer
a664InitPayload (testMsg); 	// set payload to last known signal values
a664TriggerMessage(testMsg, 1);

a664Message TESTMSG_ALLTYPES testMsg = { msgChannel = 1};
testMsg.VFG_OIL_TEMP_AB_32 = 86;
a664SetStringSignal(TEST_STRING14_CITY, "STR126", testMsg);
a664TriggerMessage(testMsg, 1);
```
