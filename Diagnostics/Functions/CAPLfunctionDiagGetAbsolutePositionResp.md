[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetAbsolutePositionResp.md)

## CAPL Functions » Diagnostics » diagGetAbsolutePosition, diagGetAbsolutePositionResp

### Function Syntax

```c
long DiagGetAbsolutePosition(diagRequest request, char parameterPath[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 1
long DiagGetAbsolutePosition(diagResponse response, char parameterPath[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 2
long DiagGetAbsolutePositionResp(diagRequest request, char parameterPath[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 3
long DiagGetAbsolutePosition(diagRequest request, char complexParam[], dword iteration, char leafParameter[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 4
long DiagGetAbsolutePosition(diagResponse response, char complexParam[], dword iteration, char leafParameter[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 5
long DiagGetAbsolutePositionResp(diagRequest request, char complexParam[], dword iteration, char leafParameter[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 6
```

### Method Syntax

```c
long diagRequest::GetAbsolutePosition(char parameterPath[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 1
long diagResponse::GetAbsolutePosition(char parameterPath[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 2
long diagRequest::GetAbsolutePositionResp(char parameterPath[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 3
long diagRequest::GetAbsolutePosition(char complexParam[], dword iteration, char leafParameter[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 4
long diagResponse::GetAbsolutePosition(char complexParam[], dword iteration, char leafParameter[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 5
long diagRequest::GetAbsolutePositionResp(char complexParam[], dword iteration, char leafParameter[], dword& bytePosOut, dword& bitPosOut, dword& bitConsumptionOut); // form 6
```

### Description

Retrieves the position of a parameter in its primitive. The parameter may be located in a specific iteration in the primitive (forms 4-6) or in the response stored for a request (forms 3 and 6).

### Parameters

- **request, response**: Object in which the parameters are located.
- **parameterPath**: Path of the parameter in the primitive (forms 1-3).
- **complexParam**: Complex parameter (forms 4-6).
- **iteration**: Iteration within the complex parameter that is referenced (forms 4-6).
- **leafParameter**: Leaf parameter within the referenced iteration in the complex parameter (forms 4-6).
- **bytePosOut**: Returns the position of the first byte of the parameter in the primitive.
- **bitPosOut**: Returns the number of the bit in the first byte where the parameter starts.
- **bitConsumptionOut**: Returns the length of the parameter in bits.

### Return Values

- **0**: success
- **`< 0`**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example

```plaintext
{
  dword bytePos;
  dword bitPos;
  dword bitLen;

  if( 0 == this.GetAbsolutePosition( "SpecialParameter", bytePos, bitPos, bitLen))
    write( "Special parameter is located at [%u:%u], bytePos, bitPos);
  else
    write( "Special parameter is not located in response primitive.");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
