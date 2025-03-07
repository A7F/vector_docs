[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagStartGenerateKeyFromSeed.md)

**CAPL Functions** » **Diagnostics** » **diagStartGenerateKeyFromSeed**

# diagStartGenerateKeyFromSeed

**Valid for:** CANoe DE

## Function Syntax

```plaintext
long diagStartGenerateKeyFromSeed(byte seedArray[], dword seedArraySize, dword securityLevel); // form 1
long diagStartGenerateKeyFromSeed(byte seedArray[], dword seedArraySize, dword securityLevel, char variant[], char option[]); // form 2
long diagStartGenerateKeyFromSeed(char ecuQualifier[], byte seedArray[], dword seedArraySize, dword securityLevel); // form 3
long diagStartGenerateKeyFromSeed(char ecuQualifier[], byte seedArray[], dword seedArraySize, dword securityLevel, char variant[], char option[]); // from 4
```

## Description

Starts generation of the security key from the seed using a Seed & Key DLL. Returns an error if computation could not be started.

The result of the computation is indicated by a call to the function [_Diag_GenerateKeyResult](CAPLfunctionDiagGenerateKeyResult.md). Note that the computation of a security key might take longer than 1 ms, which would cause problems with realtime event processing in CANoe DE product. Therefore the computation is done in the background, i.e. the result is not available immediately. In tester nodes it is possible to use the function [TestWaitForGenerateKeyFromSeed](../../Test/Functions/CAPLfunctionTestWaitForGenerateKeyFromSeed.md). If the computation is guaranteed to take much less than 1 ms, [diagGenerateKeyFromSeed](CAPLfunctionDiagGenerateKeyFromSeed.md) may be used.

## Parameters

- **seedArray**: Seed bytes as returned by the ECU.
- **seedArraySize**: Number of bytes in the seedArray, as returned by the ECU.
- **securityLevel**: Security level for which the key will be created.
- **variant**: Variant qualifier as defined in the diagnostic description. In the first form of the function, this value will be the variant configured for the diagnostic description.
- **option**: Further options that will be forwarded to the DLL. If not present or an empty string, the value might be derived from the state of the communication, e.g. the diagnostics session the ECU is in.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

- **0**: If computation was started
- **otherwise**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
_Diag_GenerateKeyResult( long result, BYTE computedKey[])
{
  diagRequest ECU.KeyLevel_0x01_Send rqSendKey;

  if( 0 != result)
  {
    write( "Error: computing key returned %d", result);
    return;
  }

  // Success, i.e. a key was computed, so send it to the ECU

  rqSendKey.SetParameterRaw( "SecurityKey", computedKey, elcount(computedKey));
  rqSendKey.SendRequest();
}

on diagResponse ECU.SeedLevel_0x01_Request
{
  BYTE seed[2];
  long count;

  count = this.GetParameterRaw( "SecuritySeed", seed, elcount(seed));
  diagStartGenerateKeyFromSeed( "ECU", seed, elcount( seed), 1, "variant", "option");
}

on key 'u' // unlock
{
  diagRequest ECU.SeedLevel_0x01_Request rqRequestSeed;
  rqRequestSeed.SendRequest();
}
```

[Seed & Key DLL / Security Access](../../../CANoeCANalyzer/Diagnostics/Special/DiagSecurityDLLAccess.md) • [_Diag_GenerateKeyResult](CAPLfunctionDiagGenerateKeyResult.md) • [diagGenerateKeyFromSeed](CAPLfunctionDiagGenerateKeyFromSeed.md) • [TestWaitForGenerateKeyFromSeed](../../Test/Functions/CAPLfunctionTestWaitForGenerateKeyFromSeed.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)