[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILOnCA.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILOnCA

# J1939ILOnCA (Callback)

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILOnCA(long newAddress)
```

## Description

This callback function is called from the J1939 IL when a Command Address message is received. The assignment of the new address can be suppressed.

## Parameters

- **newAddress**
  - 0 – 253: new address that ECU can accept
  - 254: ECU has to go offline

## Return Values

- **1**: accept the new address
- **0**: don’t accept the new address

## Example

```plaintext
long J1939ILOnCA(long address)
{
  if(address == 2)
    return 0; // don’t accept the address ‘2’
  else
    return 1;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)