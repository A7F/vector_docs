[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetP2ExtendedDiagSetP2Extended.md)

## diagGetP2Extended, diagSetP2Extended

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetP2Extended, diagSetP2Extended

### Function Syntax

- `long diagGetP2Extended ();` // form 1: deprecated. Is equivalent to form 2 with source value 2.
- `long diagGetP2Extended (dword source);` // form 2
- `long diagSetP2Extended (long timeout);` // form 3
- `long DiagGetP2Extended(char ecuQualifier[], long isTester, dword source);` // form 4

### Description

Returns the **P2 extended** timeout from the selected source, or sets it to the specified value.

**Note**: This function can only be used in combination with the CAPL Callback Interface. In this case you can use [diagSetTimeout](CAPLfunctionDiagSetTimeout.md) to specify the request timeout. When the built-in diagnostic channel is used, the function [diagSetP2Timeouts](CAPLfunctionDiagSetP2Timeouts.md) must be used to set P2 and P2-extended together.

### Parameters

- **timeout**
  - `-1`: Deactivates "Response Pending" handling.
  - `0`: Resets P2ex to its preset value.
  - `>0`: Sets P2ex to the value (in ms).

  **Note**: If "Response Pending" handling is deactivated, CANoe DE product forwards these responses to CAPL as negative responses. Otherwise, the P2ex timer is automatically started and the final response or a timeout is reported.

- **source**
  - `0`: Currently active value, i.e., the value originally set or last set from CAPL.
  - `1`: Value stored at the selected interface in the description's document.
  - `2`: Value configured in the configuration dialog for the description.
  - `other`: reserved

  **Note**: Basic diagnostic devices do not have an interface defined in a description, therefore source=1 will return the value set at the configuration (source=2).

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

- **isTester**
  - `0`: The node asking for the communication parameter is an ECU simulation.
  - `1`: The node asking for the communication parameter is a tester.
  - `other`: reserved

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or time in ms for **DiagGetP2Extended**.

### Example

```plaintext
diagSetTarget("ECU1");
write("Current P2 = %d", diagGetP2Extended(0));
write("Original value at interface = %d", diagGetP2Extended(1));
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
