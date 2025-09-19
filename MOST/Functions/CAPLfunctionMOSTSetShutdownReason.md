[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetShutdownReason.md)

## CAPL Functions » MOST » mostSetShutdownReason

### Function Syntax

```plaintext
mostSetShutdownReason(long channel, long reason);
```

### Description

Sets the shutdown reason value. This function is needed for resetting the shutdown reason value to 0x00 (No result available).

**Note**: It is recommended to call this function from the [OnMostShutdownReason](../EventProcedures/CAPLfunctionOnMostShutdownReason.md) event procedure.

### Parameters

- **channel**: Channel of the connected interface.
- **reason**: The reason code for the last shutdown.
  - 0: No result available

### Return Values

- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

### Example

—

[OnMostShutdownReason](../EventProcedures/CAPLfunctionOnMostShutdownReason.md) • [mostGetShutdownReason](CAPLfunctionMOSTGetShutdownReason.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
