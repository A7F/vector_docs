[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagCheckObjectMatch.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagCheckObjectMatch

# diagCheckObjectMatch

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagCheckObjectMatch( diagRequest request, diagResponse response);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long diagRequest::CheckObjectMatch( diagResponse response);
```

## Description

Checks if the response service id is a valid (positive or negative) response for the request.

## Parameters

- **request**: Diagnostics request
- **response**: Diagnostics response

## Return Values

- **1**: Objects match.
- **0**: Objects do not match.

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
DiagRequest AirbaContr_Read req;
DiagResponse AirbaContr_Read resp;

if( 1 == diagCheckObjectMatch( req, resp))
    write( "Request and response match!");
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)