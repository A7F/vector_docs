[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetActiveVariant.md)

**CAPL Functions** » **Diagnostics** » **diagGetActiveVariant**

# diagGetActiveVariant

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetActiveVariant(char outputBuffer[], dword bufferSize); // form 1`
- `long diagGetActiveVariant(char ecuQualifier[], char outputBuffer[], dword bufferSize); // form 2`

## Description

Returns the currently active variant.

## Parameters

- **ecuQualifier**: If given, returns the active variant of this target. If omitted, the target formerly set by [diagSetTarget](CAPLfunctionDiagSetTarget.md) is used.
- **outputBuffer**: Output field
- **bufferSize**: Size of the output buffer

## Return Values

- Length of qualifier written to buffer, may be truncated.
- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
testcase SetActiveVariantFromSystemVariable()
{
  char variantName[100];
  char outputBuffer[100];
  long retVal;
  diagSetTarget("ECU");

  retVal = sysGetVariableString(sysvar::VariantSwitch::VariantToUse,
  variantName, elcount(variantName));

  if( 0 > retVal)
  {
    testStepFail("", "Could not get variant name from system variable (%d)", retVal);
  }

  retVal = testWaitForDiagChangedActiveVariant(variantName);

  if(0 >= retVal)
  {
    diagGetErrorString(retVal, outputBuffer, elcount(outputBuffer));
    testStepFail("", "Error %d when changing variant (%s)", retVal, outputBuffer);
  }
}

testcase SwitchToIdentifiedVariant()
{
  char variantName[100];
  char outputBuffer[100];
  long retVal;

  diagSetTarget("ECU");

  retVal = testWaitForDiagSetIdentifiedVariant();

  if(0 >= retVal)
  {
    diagGetErrorString(retVal, outputBuffer, elcount(outputBuffer));
    testStepFail("", "Error %d while setting identified variant (%s)", retVal, outputBuffer);
  }

  retVal = diagGetActiveVariant(variantName, elcount(variantName));

  if( 0 > retVal)
  {
    testStepFail("", "Could not get active Variant");
  }

  sysSetVariableString(sysvar::VariantSwitch::ActiveVariant, variantName);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)