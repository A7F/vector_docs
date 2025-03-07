[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagInterpretAs.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagInterpretAs

# diagInterpretAs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagInterpretAs( diagResponse response, char primitiveQualifier[]);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
diagResponse::InterpretAs( char primitiveQualifier[]);
```

## Description

Treats the data of the response object as the specified primitive. This will cause a reinterpretation of the data, but the data will **not** be changed.

**Note**: The specified primitive must be defined for the service the response currently refers to! Please refer to [diagnostic descriptions with overloaded responses](../CAPLfunctionsDiagnosticsDescriptionsOverloadResponses.md) for details.

## Parameters

- **response**: Diagnostics object
- **primitiveQualifier**: Qualifier of the service primitive that should be used for reinterpretation.

## Return Values

- **0**: No error, OK
- **<0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

This function determines the actual response primitive by trying to set the interpretation of the argument to the defined variations. 0 is returned if interpretation is possible.

```plaintext
long FindCorrectInterpretation( diagResponse * response)
{
    if( !response.InterpretAs( "ServiPR"))
        return 0; // no error -> interpretation OK
    if( !response.InterpretAs( "ServiEcu1PR"))
        return 0; // no error -> interpretation OK
    if( !response.InterpretAs( "ServiDefauD"))
        return 0; // no error -> interpretation OK
    // None of the known primitives matches, so return failure
    return -1; // not found
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)