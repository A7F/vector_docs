[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetLastError.md)

**CAPL Functions** » **Car2x** » **C2xGetLastError**

# C2xGetLastError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xGetLastError(void);
```

## Description

Returns the error code of the last called C2x… function.

## Parameters

—

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
char error[100];
long value;
long packetHandle;

value = C2xGetTokenInt(packetHandle, "eth", "type");
if (C2xGetLastError() == 0) {
  write("Ethernet Type is 0x%x", value);
} else {
  C2xGetLastErrorText(elCount(error), error);
  write("Error: %s", error);
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)