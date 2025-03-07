[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagCheckValidRespPrimitive.md)

**CAPL Functions** » **Diagnostics** » **diagCheckValidRespPrimitive**

# diagCheckValidRespPrimitive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagCheckValidRespPrimitive( diagRequest obj);`
- `long diagCheckValidRespPrimitive( diagRequest obj, dword reasonOut[]);`
- `long diagCheckValidRespPrimitive( diagRequest obj, char primitiveQualifier[]);`
- `long diagCheckValidRespPrimitive( diagRequest obj, char primitiveQualifier[], dword reasonOut[]);`

## Method Syntax

- `long diagRequest::CheckValidRespPrimitive();`
- `long diagRequest::CheckValidRespPrimitive(dword reasonOut[]);`
- `long diagRequest::CheckValidRespPrimitive( char primitiveQualifier[]);`
- `long diagRequest::CheckValidRespPrimitive( char primitiveQualifier[], dword reasonOut[]);`

## Description

Checks if the response received for the request matches its specification in the diagnostic description. If a primitive qualifier is given, the definition of that primitive at the object's service is used as specification.

**Note**: If a primitive is specified, it must be defined for the service the response currently refers to! Please refer to [diagnostic descriptions with overloaded responses](../CAPLfunctionsDiagnosticsDescriptionsOverloadResponses.md) for details.

## Parameters

- **obj**: Diagnostics object to check.
- **reasonOut**: Optional output parameter field for fail reason.
- **primitiveQualifier**: Qualifier of the service primitive that should be used as specification.

## Return Values

- **1**: Response received for the request matches its specification in the diagnostic description.
- **0**: Response received for the request does not match its specification. In this case, `reasonOut[0]` will indicate the problem:
  - 1: data too long
  - 2: data too short
  - 3: constant overwritten
  - 4: unknown format error
  - 5: illegal parameter value found
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
if( 1 == request.CheckValidRespPrimitive( "ServiDefauD"))
   TestStepPass( "Is default response");
else
   TestStepFail( "Not default response");
```

[diagCheckValidPrimitive](CAPLfunctionDiagCheckValidPrimitive.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)