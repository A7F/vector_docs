[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBDevOpen.md)

[CAPL Functions](../../CAPLfunctions.md) » [GPIB](../CAPLfunctionsGPIBOverview.md) » GPIBDevOpen

# GPIBDevOpen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long GPIBDevOpen (long boardIdx, long primAddr, long secAddr, long timeout, long eot, long eos);
```

## Description

Opens a GPIB device and returns a device ID.

## Parameters

- **boardIdx**: Index of the GPIB board (e.g.0)
- **primAddr**: Primary address of the GPIB device (0..30)
- **secAddr**: Secondary address of the GPIB device (96..126, typical: 0)
- **timeout**: Timeout of the device. This indicates the maximum duration of an I/O operation. If this time expires before the operation has ended the function rolls back with a timeout error in the status word.

  **Attention**: The value for Timeout must be > 0! (typically: 10 s)

  - 0: Timeout disabled. **Do not use!**
  - 1: Timeout = 10 us
  - 2: Timeout = 30 us
  - 3: Timeout = 100 us
  - 4: Timeout = 300 us
  - 5: Timeout = 1 ms
  - 6: Timeout = 3 ms
  - 7: Timeout = 10 ms
  - 8: Timeout = 30 ms
  - 9: Timeout = 100 ms
  - 10: Timeout = 300 ms
  - 11: Timeout = 1 s
  - 12: Timeout = 3 s
  - 13: Timeout = 10 s
  - 14: Timeout = 30 s
  - 15: Timeout = 100 s
  - 16: Timeout = 300 s
  - 17: Timeout = 1000 s

- **eot**: Indicates whether the GPIB EOI line should be set at the end of a write operation. Values: 0, 1 (typical: 1)
- **eos**: Configuration of "end-of-string" behavior. For further information please refer to documentation for your GPIB controller. Typical value: 0

## Return Values

- **Device ID**:
- **-1**: On error
  - if no GPIB driver is available, or
  - if the driver is not properly installed, or configured incorrectly, or
  - if the function is called outside the preStart function of a CAPL program.

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
