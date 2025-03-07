[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetLastResponse.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetLastResponse

# diagGetLastResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The output object must first be declared with any desired qualifier path, however after use in this function it may correspond to any desired diagnostic service. Therefore extra caution should be exercised when accessing the object’s parameters.

## Function Syntax

```
long diagGetLastResponse (diagRequest req, diagResponse respOut);
long diagGetLastResponse (diagResponse respOut);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
long diagRequest::GetLastResponse (diagResponse respOut);
long diagResponse::GetLastResponse ();
```

## Description

Saves the last response received (for the specified request) in the output object.

## Parameters

- **req**: Request
- **respOut**: Output object for the received response

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [diagGenerateKeyFromSeed](CAPLfunctionDiagGenerateKeyFromSeed.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)