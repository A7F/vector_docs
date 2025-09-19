[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetProtectedID.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetProtectedID

# linGetProtectedID

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linGetProtectedID (long frameID);
```

## Description

With this function it is possible to calculate protected ID for the corresponding LIN frame identifier (i.e. the frame identifier with parity bits).

## Parameters

- **frameID**: LIN frame identifier whose protected ID will be calculated.  
  Value range: 0 .. 63

## Return Values

Returns the calculated protected identifier or a value greater than 255 on failure.

## Example

Display in Write Window a protected ID for each LIN frame seen on the bus

```plaintext
on linFrame *
{
  dword pid;
  pid = linGetProtectedID(this.ID);
  writeLineEx(0,0, "Protected ID for LIN frame identifier 0x%x is 0x%x", this.ID, pid);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
