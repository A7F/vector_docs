[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkConfigSetPrecision.md)

**CAPL Functions** » **Test Service Library** » **Configuration Functions** » **ChkConfig_SetPrecision**

# ChkConfig_SetPrecision

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long ChkConfig_SetPrecision(unsigned int aPrecision);
```

## Description

This function configures the TSL time basis for the current node. The time basis (precision) affects all future times that are passed when creating checks (see [check descriptions](../../../TestCommands/CheckDescriptions.md)), and it affects the time basis for queries ([status report functions](../CAPLfunctionsTSLStatusReportFunctions.md)).

This function allows you to configure the time basis for new checks to be created. The time bases of checks that have already been created are not changed by this function. They can be polled by a special query.

## Parameters

- **aPrecision**: Describes the decimal power of the precision  
  Value range: 2 < aPrecision < 10

  - 3: 10`<sup>`–3</sup> seconds = ms (default)
  - 4: 10`<sup>`–4</sup> seconds
  - 5: 10`<sup>`–5</sup> seconds = 10 us: e.g. used in trace export
  - 6: 10`<sup>`–6</sup> seconds = us
  - 7: 10`<sup>`–7</sup> seconds
  - 8: 10`<sup>`–8</sup> seconds
  - 9: 10`<sup>`–9</sup> seconds = ns

## Return Values

- **0**: successful
- **-1**: invalid range of precision
- **-3**: TSL was not initialized

## Example

```plaintext
// precision of the test is set to us
chkConfig_SetPrecision(6);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
