[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetP6ExtendedDiagGetSetP6Timeout.md)

## CAPL Functions » Diagnostics » diagGetP6Extended, diagGetP6Timeout, diagSetP6Timeouts

### Valid for: CANoe DE

**Note:** These functions only work if the tester program uses the built-in DoIP channels!

### Function Syntax

- `long DiagGetP6Extended(dword source); // form 1`
- `long DiagGetP6Extended(char ecuQualifier[], dword source); // form 2`
- `long DiagGetP6Timeout(dword source); // form 3`
- `long DiagGetP6Timeout(char ecuQualifier[], dword source); // form 4`
- `long DiagSetP6Timeouts(dword newP6_ms, dword newP6ex_ms); // form 5`
- `long DiagSetP6Timeouts(char ecuQualifier[], dword newP6_ms, dword newP6ex_ms); // form 6`

### Description

Returns or sets the time **P6** and **P6ex** (in milliseconds) from the given source. If an ECU qualifier is given, the built-in communications channel for this target is accessed. When a Diagnostics over IP target is active, the P2 timeouts cannot be used because a TCP/IP connection does not provide end of transmission and start of reception events. Therefore, the P2 functionality cannot be implemented and the overall timeout P6 has been defined.

### Parameters

- **source**

  - **Value:** Description
    - `0`: Currently active value, i.e., the value originally set or last set from CAPL
    - `1`: Value stored at the selected interface in the description's document
    - `2`: Value configured in the configuration dialog for the description
    - `other`: reserved

  **Note:** Basic diagnostic devices do not have an interface defined in a description, therefore source=1 will return the value set at the configuration (source=2).

- **ecuQualifier**

  Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

- **newP6_ms, newP6ex_ms**

  The DTL diagnostics communication channel uses these timeouts (in milliseconds) from now on.

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example

—
