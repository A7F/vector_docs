[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetTokenLengthBit.md)

**CAPL Functions** » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxGetTokenLengthBit

# AfdxGetTokenLengthBit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetTokenLengthBit( long packet, char protocolDesignator[], char tokenDesignator[] );
```

## Description

This function returns the length of a token in bit.

## Parameters

- **packet**: handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md)
- **protocolDesignator**: name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "afdx"
- **tokenDesignator**: name of the token, e.g. "header"

## Return Values

- length of the token in bit
- With [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md) you have to check if the function has been processed successfully.

## Example

```plaintext
long packet = 0;
long len = 0;
char error[100];

packet = AfdxInitPacket( "afdx" );
len = AfdxGetTokenLengthBit( packet, "afdx", "data" );
if (AfdxGetLastError() == 0)
{
  // do something with len
}
else
{
  AfdxGetLastErrorText( elCount(error), error );
  write("Error: %s", error );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)