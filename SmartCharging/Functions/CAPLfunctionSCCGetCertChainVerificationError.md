[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetCertChainVerificationError.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » SCC_GetCertChainVerificationError

# SCC_GetCertChainVerificationError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_GetCertChainVerificationError (dword Index, char CertName[], dword& ErrorCode)
```

## Description

Gets an individual verification from the last certificate chain verification, which is indicated by the callback function [SCC_CertChainVerificationInd](../Callbacks/CAPLfunctionSCCCertChainVerificationInd.md).

## Parameters

- **Index**: Number of the queried error < SCC_GetCertChainVerificationErrorCount().
- **CertName**: Queries the name of the verified certificate (to the given char buffer). The same certificate may be returned multiple times with different error codes.
- **ErrorCode**: Gets the number of the found error, which can be evaluated as follows (via reference):

  1. Certificate serial negative
  2. Distinguished Name too long
  3. Signature method too weak
  4. Untrusted hash
  5. Certificate not yet valid
  6. Certificate has expired
  7. Certificate issuer not found
  8. Cannot establish trust
  9. Certificate chain loop
  10. Chain lacks trusted root
  11. Chain name mismatch
  12. Policy error
  13. Invalid usage
  14. Certificate chain too long
  15. Certificate issuer is not a valid CA
  16. Name constraint error
  17. Certificate issuer not found
  18. Unknown critical extension
  19. Duplicate certificate extension
  20. Invalid X.509v3 extension in v1 or v2 certificate
  21. Duplicate certificate policy
  22. X.509v2 identifiers in v1 certificate
  23. Signature error
  24. Certificate public key invalid
  25. Signature algorithm unknown
  26. Signature algorithm – bad parameters
  27. Domain Component invalid according to ISO 15118-2
  28. Common Name mismatch (Common Name of leaf does not match received eMAID)
  29. Country Name was set within contract certificate

## Return Values

- **1**: if successful
- **0**: else

## Example

```plaintext
SCC_CertChainVerificationInd( byte SessionId[], char ChainName[], dword Result )
{
  int i;
  char certName[255];
  dword errorCode;

  if (Result == 0)
  {
    for (i = 0; i < SCC_GetCertChainVerificationErrorCount(); ++i)
    {
      SCC_GetCertChainVerificationError(i, certName, errorCode);

      WriteLineEx(1 /* CAPL */, 2 /* warning */, "Certificate %s of %s verified with Error: %i", certName, chainName, errorCode);
    }
  }
}
```

[SCC_CertChainVerificationInd](../Callbacks/CAPLfunctionSCCCertChainVerificationInd.md)  •  [SCC_GetCertChainVerificationErrorCount](CAPLfunctionSCCGetCertChainVerificationErrorCount .md)
