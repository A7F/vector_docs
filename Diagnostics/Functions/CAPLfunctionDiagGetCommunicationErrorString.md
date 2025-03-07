[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetCommunicationErrorString.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetCommunicationErrorString

# diagGetCommunicationErrorString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long DiagGetCommunicationErrorString( long communicationError, char descriptionOut, dword bufferLen);
```

## Description

Returns a description for the given communication error.

## Parameters

- **communicationError**: Value returned by [diagGetLastCommunicationError](CAPLfunctionDiagGetLastCommunicationError.md).
- **descriptionOut**: Output buffer for the meaning of the communication error.
- **bufferLen**: Capacity of the output buffer.

## Return Values

Number of characters written to the buffer.

## Example

```plaintext
...
if (0 == TestWaitForDiagResponse( req, 2000))
{
  char errStr[100];
  err = DiagGetLastCommunicationError();
  DiagGetCommunicationErrorString( err, errStr, elcount(errStr));
  write("LastCommunicationError=%d - %s", err, errStr);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)