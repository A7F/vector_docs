[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRSendSymbol.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSendSymbol

# frSendSymbol

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
frSendSymbol( long <type>, long <param>, int channel );
```

## Description

This function sends an MTS symbol in the next possible symbol window if the Communication Controller is in normal mode (synchronized).

## Parameters

- **<type>**: Not used at this time. Reserved for future expansions. Should always be equal to 0.
- **<param>**: Not used at this time. Reserved for future expansions. Should always be equal to 0.
- **channel**: Channel number (or cluster number)

## Return Values

—

## Example

This example sends a MTS symbol when a key is pressed in the next possible cycle.

```plaintext
on key 'm'
{
   frSendSymbol(0 /* not used */, 0 /* not used */, %CHANNEL%);
}
```

**Note**

The cluster parameters must define a symbol window! A CAS cannot be sent explicitly. It is reserved for the start-up procedure. For sending a wake-up see function [resetFlexRayCCEx](CAPLfunctionResetFlexrayCCEX.md).

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)