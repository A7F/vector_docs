[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetP2Timeout.md)

## CAPL Functions » Diagnostics » diagGetP2Timeout

### Function Syntax

- `long diagGetP2Timeout ();` // form 1: deprecated. Is equivalent to form 2 with source value 2.
- `long diagGetP2Timeout ( dword source );` // form 2
- `long diagGetP2Timeout (char ecuQualifier[], dword bIsTester, dword source );` // form 3

### Description

Returns the time P2 in milliseconds, from the given source.

If an ECU qualifier is given, the build-in communications channel for this target is accessed.

**P2**: Time between sending of the request and the start of the arrival of the first response.

**Note**: The function will return different values for client (i.e. in a tester) and server (i.e. in an ECU simulation).

### Parameters

- **source**
  - **Value**: 0
    - Currently active value, i.e. the value originally set or last set from CAPL
  - **Value**: 1
    - Value stored at the selected interface in the description's document
  - **Value**: 2
    - Value configured in the configuration dialog for the description
  - **Value**: other
    - reserved

  **Note**: Basic diagnostic devices do not have an interface defined in a description, therefore source=1 will return the value set at the configuration (source=2).

- **ecuQualifier**
  - Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

- **bIsTester**
  - **Value**: 0
    - Get value for ECU side
  - **Value**: 1
    - Get value for tester side
  - **Value**: other
    - reserved

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or time in ms.

### Example

```plaintext
diagSetTarget( "ECU1");
write( "Current P2 = %d", diagGetP2Timeout(0));
write( "Configured P2 = %d", diagGetP2Timeout(2));
```
