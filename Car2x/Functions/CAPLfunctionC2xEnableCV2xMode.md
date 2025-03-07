[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xEnableCV2xMode.md)

**CAPL Functions** » Car2x » C2xEnableCV2xMode

# C2xEnableCV2xMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xEnableCV2xMode ( long appChannel );
```

## Description

This function enables the CV2x protocol for a channel. The function has to be called in the event handler **on preStart**.

## Parameters

- **appChannel**
  - 0 = current Channel
  - 1 = Ath1
  - 2 = Ath2

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
on preStart()
{
  // enable CV2x for the first channel (Ath1)
  C2xEnableCV2xMode (1);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)