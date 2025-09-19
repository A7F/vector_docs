[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPOnKeyActivation.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPOnKeyActivation

# Iso11783OPOnKeyActivation (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783OPOnKeyActivation( dword ecuHandle, 
 dword objectID, dword parentID, dword keyCode, dword activation );
```

## Description

The function is called by the node layer, if the user presses a soft key or button.

## Parameters

- **ecuHandle**: Handle of the ECU
- **objectID**: Object ID of a soft key or button object
- **parentID**: Object ID of the mask object
- **keyCode**: Code of the soft key or button
- **activation**: Activation code
  - 0: Key is release
  - 1: Key is pressed
  - 2: Key is held
  - 3: Press is canceled

## Return Values

—

## Example

```plaintext
void Iso11783OPOnKeyActivation( dword handle, dword object ID, dword parentID, dword keyCode, 
 dword activation )
{
  if (activation == 1) {
    switch(keyCode) {
      case 1: DoSometing1(); break;
      case 2: DoSometing2(); break;
    }
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
