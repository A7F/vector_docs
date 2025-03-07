[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetSendingMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetSendingMode

# diagGetSendingMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The sending as UUDT is activated via CDD and only available for special manufacturers.

## Function Syntax

```plaintext
long diagGetSendingMode 
(diagResponse response);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
diagResponse::GetSendingMode ()
```

## Description

Delivers information about the send mode of the answer.

## Parameters

- **response**: Response

## Return Values

- **0**: The answer should be sent "physically".
- **1**: The answer should be sent as UUDT.

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)