[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPOnResponse.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » **Iso11783OPOnResponse**

# Iso11783OPOnResponse (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783OPOnResponse( dword ecuHandle, pg VTtoECU response );
```

## Description

The function is called by the node layer, if a response from the Virtual Terminal is received. If a response is **not** received, the callback function [Iso11783OPOnError](CAPLfunctionIso11783OpOnError.md) is called.

## Parameters

- **ecuHandle**: Handle of the ECU
- **response**: Parameter group containing the answer of the Virtual Terminal

## Return Values

—

## Example

```plaintext
void Iso11783OPOnResponse( dword handle, pg VTtoECU response )
{
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)