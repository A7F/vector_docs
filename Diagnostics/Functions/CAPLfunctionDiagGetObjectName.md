[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetObjectName.md)

**CAPL Functions** » **Diagnostics** » **diagGetObjectName**

# diagGetObjectName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagGetObjectName( diagResponse obj, char nameBufferOut[], dword nameBufferLen);
long diagGetObjectName( diagRequest obj, char nameBufferOut[], dword nameBufferLen);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
long diagRequest::GetObjectName( char nameBufferOut[], dword nameBufferLen);
long diagResponse::GetObjectName( char nameBufferOut[], dword nameBufferLen);
```

## Description

Writes the language dependent name of the diagnostics object into the buffer. For ODX descriptions, this is the "long name".

## Parameters

- **obj**: Diagnostics object
- **nameBufferOut**: Output buffer
- **nameBufferLen**: Output buffer size

## Return Values

- Length of service name written to buffer, may be truncated.
- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
DiagRequest AirbaContr_Read req;
char name[100];
DiagGetObjectName( req, name, elcount( name));
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)