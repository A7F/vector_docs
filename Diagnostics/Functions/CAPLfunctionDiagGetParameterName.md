[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetParameterName.md)

**CAPL Functions** » **Diagnostics** » **diagGetParameterName**

# diagGetParameterName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagGetParameterName (diagResponse obj, dword paramNo, char buffer[], dword buffersize)
long diagGetParameterName (diagRequest obj, dword paramNo, char buffer[], dword buffersize)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long diagResponse::GetParameterName (dword paramNo, char buffer[], dword buffersize)
long diagRequest::GetParameterName (dword paramNo, char buffer[], dword buffersize)
```

## Description

Writes the qualifier (without parent path) of the diagnostic parameter into the given field. Structural parameters are counted too.

## Parameters

- **obj**: Diagnostics object
- **paramNo**: Index of the parameter in the object, beginning with **0**. Structural parameter that cannot have a simple value (e.g., a container for a list) are also counted and reported.
- **buffer**: Output buffer
- **buffersize**: Buffer size

## Return Values

Number of chars written to buffer or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—

[diagGetParameterLongName, diagGetRespParameterLongName](CAPLfunctiondiagGetParameterLongName.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)