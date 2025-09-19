# DoIP_SetNextDiagnosticMessageNACKCode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetNextDiagnosticMessageNACKCode(long NACKCode);
```

## Description

Sets the next return code sent in the acknowledgment for a diagnostic message received. The code is reset to 0 (positive) after usage.

**Note**  
Values other than 0 let the peer assume that transmission failed, i.e. error handling is necessary by the peer.

## Parameters

- **NACKCode**  
  ISO 13400 defines these values (amongst others):
  - 0: Positive (default)
  - 2: Invalid source address
  - 3: Unknown target address

## Return Values

—

## Example

```plaintext
on key 'n' {
  write("The next diagnostics message will get a negative ack");
  DoIP_SetNextDiagnosticMessageNACKCode(3);
}
```
