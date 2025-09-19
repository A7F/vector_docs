[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAmsSetSizePrefixed.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAmsSetSizePrefixed

# mostAmsSetSizePrefixed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAmsSetSizePrefixed(long channel, long minlength);
```

## Description

Configures the minimum length of an AMS message above which an initiating message with TelID==4 is sent.

## Parameters

- **channel**: Channel of the connected network interface.
- **minlength**: Minimum length of an AMS message.
  - `minlength == -1`: use the size configured in the hardware configuration dialog, AMS page
  - `minlength == 0`: never send an initiating message with TelID==4
  - `minlength >= 46`: send an initiating message with TelID==4, when the length of the AMS message is >= minlength
  - Note: Maximum value of minlength is 65535 (0xFFFF), since this is the maximum size of an AMS message.

## Return Values

- **0**: OK
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

Activate special size prefix length for exactly one AMS message.

```plaintext
mostAmsSetSizePrefixed(1, 46);
mostAmsOutput(1, "Telephone.List.Status(0,1,2,3,4,5,6,7)");
mostAmsSetSizePrefixed(1, -1);
```

Activate special size prefix length for AMS messages with more than 200 bytes payload.

```plaintext
mostAmsSetSizePrefixed(1, 200);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
