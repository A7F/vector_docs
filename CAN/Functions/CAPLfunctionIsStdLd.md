[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionIsStdLd.md)

**CAPL Functions** » **CAN** » **isStdId, isExtId**

# isStdId, isExtId

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long isStdId(dword id);`
- `long isStdId(message m);`
- `long isExtId(dword id);`
- `long isExtId(message m);`

## Description

Checks parameter for [extended identifier](../../../CANoeCANalyzer/General/CANExtendedIdentifier.md) (29 bit) or standard identifier (11 Bit).

## Parameters

- **message**: Variable of type message
- **id**: Id part of a message

## Return Values

1 if check was successful, else 0

## Example

```plaintext
...
if(isExtId(this))
    write("extended identifier");
else
    write("standard identifier");
or
std = isStdId(m100.id);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)