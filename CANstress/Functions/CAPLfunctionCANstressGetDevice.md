# CANstressGetDevice

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CANstressGetDevice ();
```

## Description

Sends back the handle for the current CANstress device.

## Parameters

—

## Return Values

- **> 0**  
  If successful.  
  Handle for the current CANstress device.

- **-1**  
  In case of error.  
  **DeviceId** does not contain a valid handle for a CANstress device. You might get this result, for example, if **CANstressCreateServer** has not yet been called.

## Example

—
