[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDgetlasterrortext.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783PDDGetLastErrorText

# Iso11783PDDGetLastErrorText

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDGetLastErrorText( dword bufferSize, char buffer[] );
```

## Description

This function returns as a string the error description of the function of this node layer most recently executed.

## Parameters

- **bufferSize**: Size of the buffer into which the error text is copied
- **buffer**: Buffer in which error text is copied

## Return Values

Number of characters copied

## Example

```plaintext
char text[256];

value = Iso11783PDDGetValue ( ecuHandle, PD::AppRateSignal, 0;

if (Iso11783PDDGetLastError () != 0) {
  Iso11783PDDGetLastErrorText( elCount(text), text );
  write( "ERROR: %s", text );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)