# coTfsNmtWaitForBootupMessage (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsNmtWaitForBootupMessage( void );
```

## Description

This function waits for the boot-up message.

**Note**: If the heartbeat producer is already active, it will be restored at the end.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
/* wait for a bootup message */
if (coTfsNmtWaitForBootupMessage() == 1) {
  write("Bootup message received");
}
```
