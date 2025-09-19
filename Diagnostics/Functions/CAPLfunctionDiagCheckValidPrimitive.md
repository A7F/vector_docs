# diagCheckValidPrimitive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagCheckValidPrimitive( diagRequest obj);`
- `long diagCheckValidPrimitive( diagRequest obj, dword reasonOut[]);`
- `long diagCheckValidPrimitive( diagResponse obj);`
- `long diagCheckValidPrimitive( diagResponse obj, dword reasonOut[]);`
- `long diagCheckValidPrimitive( diagResponse obj, char primitiveQualifier[]);`
- `long diagCheckValidPrimitive( diagResponse obj, char primitiveQualifier[], dword reasonOut[]);`

## Method Syntax

- `long diagRequest::CheckValidPrimitive();`
- `long diagRequest::CheckValidPrimitive(dword reasonOut[]);`
- `long diagResponse::CheckValidPrimitive();`
- `long diagResponse::CheckValidPrimitive(dword reasonOut[]);`
- `long diagResponse::CheckValidPrimitive(char primitiveQualifier[]);`
- `long diagResponse::CheckValidPrimitive(char primitiveQualifier[], dword reasonOut[]);`

## Description

Checks if the given object matches its specification in the diagnostic description. If a primitive qualifier is given, the definition of that primitive at the object's service is used as specification.

**Note**: If a primitive is specified, it must be defined for the service the response currently refers to! Please refer to [diagnostic descriptions with overloaded responses](../CAPLfunctionsDiagnosticsDescriptionsOverloadResponses.md) for details.

## Parameters

- **obj**: Diagnostics object to check.
- **reasonOut**: Optional output parameter field for fail reason.
- **primitiveQualifier**: Qualifier of the service primitive that should be used as specification.

## Return Values

- **1**: Primitive matches the specification in the diagnostic description.
- **0**: Primitive does not match its specification. In this case, `reasonOut[0]` will indicate the problem:
  - **1**: data too long (not for PDX/ODX)
  - **2**: data too short
  - **3**: constant overwritten
  - **4**: unknown format error
  - **5**: illegal parameter value found
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
long ConformsToKnownPrimitives( diagResponse * response)
{
    if( 1 == response.CheckValidPrimitive( "ServiDefauD")
        || 1 == response.CheckValidPrimitive( "ServiEcu1PR"))
        return 1;
    return 0;
}
```

[diagCheckValidRespPrimitive](CAPLfunctionDiagCheckValidRespPrimitive.md)
