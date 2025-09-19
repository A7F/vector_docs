# diagGetSuppressResp, diagSetSuppressResp

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
This function resets the size of the diagnostic object to the size defined in the diagnostic description, i.e. if necessary, [diagResize](CAPLfunctionDiagResize2.md) needs to be called after calling `diagSetSuppressResp`.

## Function Syntax

```plaintext
long diagSetSuppressResp (diagRequest req, long flag); // form 1
long diagGetSuppressResp (diagRequest req); // form 2
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
diagRequest::SetSuppressResp (long flag); // form 1
diagRequest::GetSuppressResp (); // form 2
```

## Description

Under UDS (Unified Diagnostics Services), in certain requests it is possible to set the "suppressPosRspMsgIndicationBit" ("suppress positive response message indication bit"). This means that the receiver must not send any positive response. These two functions make it possible to poll and set this bit.

## Parameters

- **req**: Request
- **flag**: 0: Clear, else: Set

## Return Values

- **1**: The bit is set.
- **0**: The request does not use the bit, or it is not set.

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or value of the parameter.

## Example

—
