# TestWaitForGenerateKeyFromSeed

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForGenerateKeyFromSeed(byte seedArray[], dword seedArraySize, dword securityLevel, byte keyArray[], dword maxKeyArraySize, dword& keyArraySizeOut, dword appTimeout_ms);` // form 1
- `long TestWaitForGenerateKeyFromSeed(byte seedArray[], dword seedArraySize, dword securityLevel, char variant[], char option[], byte keyArray[], dword maxKeyArraySize, dword& keyArraySizeOut, dword appTimeout_ms);` // form 2
- `long TestWaitForGenerateKeyFromSeed(char ecuQualifier[], byte seedArray[], dword seedArraySize, dword securityLevel, byte keyArray[], dword maxKeyArraySize, dword& keyArraySizeOut, dword appTimeout_ms);` // form 3
- `long TestWaitForGenerateKeyFromSeed(char ecuQualifier[], byte seedArray[], dword seedArraySize, dword securityLevel, char variant[], char option[], byte keyArray[], dword maxKeyArraySize, dword& keyArraySizeOut, dword appTimeout_ms);` // form 4

## Description

Generates the security key from the seed using the configured **Seed and Key** DLL. The call into the DLL may need more time, therefore a test module may want to wait for the result in order not to disturb the realtime execution of the test.

## Parameters

- **seedArray**: Seed as returned from the ECU.
- **seedArraySize**: Length of the seed returned from the ECU.
- **securityLevel**: Which security level shall be unlocked?
- **variant**: Optional argument indicating the current ECU variant. In the first form this value does not have to be provided by the CAPL program, but it is taken from the diagnostic description configuration.
- **option**: Optional argument giving additional information influencing the key computation, e.g. the diagnostics session currently active. In the first form this value does not have to be provided by the CAPL program, but it is taken from the current ECU status, if configured and set.
- **keyArray**: The result of the computation is written into this array.
- **maxKeyArraySize**: Maximum key length allowed.
- **keyArraySizeOut**: Actual size of the key returned by the DLL.
- **appTimeout_ms**: Maximum time (in ms) the function waits for the computation function in the DLL to return. If the DLL needs longer than this, a timeout is reported.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

- **1**: Key generation successful
- **0**: Timeout – the DLL did not return the key in time

[Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
Testfunction ComputeKeyInExtendedSession( BYTE seed[], BYTE key[])
{
  DWORD keyLenOut;
  keyLenOut = 0;

  // The key computation may use the current session as optional argument
  TestWaitForGenerateKeyFromSeed( seed, elcount( seed), 1, key, elcount(key), keyLenOut, 1000);
}
```

[diagGenerateKeyFromSeed](../../Diagnostics/Functions/CAPLfunctionDiagGenerateKeyFromSeed.md)
