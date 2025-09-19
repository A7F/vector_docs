# diagGetResponseCode, diagGetLastResponseCode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetResponseCode (diagResponse resp);`
- `long diagGetLastResponseCode (diagRequest req);`
- `long diagGetLastResponseCode ();`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- `long diagResponse::GetResponseCode();`
- `long diagRequest::GetLastResponseCode();`

## Description

Returns the code of the specified response or last received response (for the specified request).

## Parameters

- **resp**: Response
- **req**: Request

## Return Values

- **-1**: The response was positive, i.e. there is no error code.
- **0**: No response has been received yet.
- **> 0**: Error code of the negative response.

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—
