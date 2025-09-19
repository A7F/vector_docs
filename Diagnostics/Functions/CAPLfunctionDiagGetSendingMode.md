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
