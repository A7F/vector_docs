[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/Functions/CAPLfunctionRS232OnError.md)

## RS232OnError

[CAPL Functions](../../CAPLfunctions.md) » [RS232](../CAPLfunctionsRS232Overview.md) » RS232OnError

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```
RS232OnError( dword port, dword errorFlags );
```

### Description

Callback handler for reception of errors at a serial port.

**Note**  
Will be called only at the node which issued send/receive operations. For repetitive errors (stable error condition) just the first one is returned. That case may happen for reception errors above all, i.e., at configuration mismatches of both connected ends. It is possible that in case of configuration mismatches errors may not occur at once, e.g., a configuration of 9600/8/1/no parity at one port and 115200/8/1/no parity at the other end may seem to work (though rubbish is received).

### Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **errorFlags**: Cumulative summary of what went wrong. Bits are set to flag conditions.

  - **Bit 0**: Send operation failed.
  - **Bit 1**: Receive operation failed.
  - **Bit 2**: Frame error. May be caused by parity mismatch or any other frame mismatch (e.g., number of stop bits).
  - **Bit 3**: Frame parity error. Is caused by parity mismatch.
  - **Bit 4**: Buffer overrun. It is not specified if the driver of the sender cannot send fast enough, if it is up to the receiver which got too much data in too short time or anything else.
  - **Bit 5**: Buffer overrun at receiver.
  - **Bit 6**: Break state. Other end requested to pause.
  - **Bit 7**: Timeout. May be caused by wrongly set too short timeout. See [RS232SetHandshake](CAPLfunctionRS232SetHandshake.md) for setting the timeout.

**Note**  
Several error bits may be set at the same time. Some error flags are up to the driver manufacturer what they mean and when they are issued.

### Return Values

—

### Example

```plaintext
RS232OnError(dword port, dword errorFlags)
{
   if ( errorFlags & 1 )
      writeLineEx(0,3,"send failed");
   if ( errorFlags & 2 )
      writeLineEx(0,3,"receive failed");
}
```
