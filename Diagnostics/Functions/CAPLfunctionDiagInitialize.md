[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagInitialize.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagInitialize

# diagInitialize

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```c
long diagInitialize(diagResponse object, char serviceQualifier[]); // form 1
long diagInitialize(diagResponse object, char serviceQualifier[], char primitiveQualifier[]); // form 2
long diagInitialize(diagRequest object, char serviceQualifier[]); // form 3
long DiagInitialize(diagRequest object); // form 4
long DiagInitialize(diagResponse object); // form 5
```

## Method Syntax

```c
diagResponse::Initialize(char serviceQualifier[]);
diagResponse::Initialize(char serviceQualifier[], char primitiveQualifier[]);
diagRequest::Initialize(char serviceQualifier[]);
```

## Description

Reinitializes the object for the given service or primitive. Diagnostics request will be initialized with the default request parameters of the service, while diagnostic responses will be initialized with the default parameters of the first or specified primitive of the service. If the service is not defined, or the primitive is not defined at the given service, nothing happens and an error code is returned.

**Note:**

- The data contained in the primitive is overwritten by a successful call of this function!
- Please refer to [diagnostic descriptions with overloaded responses](../CAPLfunctionsDiagnosticsDescriptionsOverloadResponses.md) for details on services defining more than one response.

## Parameters

- **object**: Diagnostics object to re-initialize
- **serviceQualifier**: Qualifier of the service that should be used for reinterpretation
- **primitiveQualifier**: Qualifier of the service primitive that should be used for reinterpretation

## Return Values

- **0**: No error, OK
- **`< 0`**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

In an ECU simulation, initialize a response object with a specific primitive before sending it.

```plaintext
on diagRequest Servi 
{
    diagResponse this response; // will be initialized with first primitive 
    response.Initialize( "Servi", "ServiEcu1PR"); // Force initialization with specific primitive 
    response.SetParameter( "Voltage", 28.0); // Access primitive specific parameter 
    response.SendResponse();
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)