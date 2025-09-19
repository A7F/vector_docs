[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineErrorInd.md)

**CAPL Functions** » **K-Line** » _KLine_ErrorInd

# _KLine_ErrorInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

_KLine_ErrorInd(dword errType)

## Description

Called when a protocol error occurred.

## Parameters

- **dword errType**: Type of the received error.

## Return Values

—

## Example

```plaintext
_KLine_ErrorInd( dword error)
{
   const cKLineErrorOffset = 100;
   char cKLineErrorText[18][76] =
   {
   "The connection is closed, thus no data processing possible",
   "Tx confirmation not received, i.e. the message was not sent in time",
   "Inter byte time (P1Min) violation from Ecu",
   "Inter byte time (P1Max) violation from Ecu",
   "P2Min time violation caused with an early Ecu response",
   "P2Max time violation caused with a late Ecu response",
   "P3Min time violation caused with an early tester request",
   "P3Max time violation caused with a late tester request",
   "Inter byte time (P4Min) violation from tester, so the processing is aborted",
   "Inter byte time (P4Max) violation from tester, so the processing is aborted",
   "Unexpected byte received, so the processing is aborted",
   "Invalid header format",
   "Wrong checksum received",
   "Frame length not matching with the header",
   "K-Line message with 0 data length",
   "Only Tx and Rx directions are supported",
   "Data was manipulated by PreSend and may not be K-Line conform",
   // Sentinel - print when no other text matches
   "(no additional information)"
   };
   long textIndex;
   textIndex = error - cKLineErrorOffset;
   if( textIndex <0 || textIndex >= elcount( cKLineErrorText))
   textIndex = elcount( cKLineErrorText) - 1;
   write("ErrorInd(%d) - %s", error, cKLineErrorText[textIndex]);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
