[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGetOperationParameterKeys.md)

**CAPL Functions** » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalGetOperationParameterKeys

# SecurityLocalGetOperationParameterKeys

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalGetOperationParameterKeys(long category, dword keyBuffer[], dword keyBufferLength)
```

## Description

Gets the list of operation parameter keys, supported by the currently loaded Security Source.

Which and how many operation parameters exist, which values are valid for an operation parameter differs from Security Source to Security Source.

Please refer to the Security Source specific manual to get more information about operation parameters. The manual can be opened from the Vector Security Manager on the OEM specific ribbon page.

## Parameters

- **long category**  
  The category of the operation parameters,  
  0 = all operation parameters.

- **dword keyBuffer[]**  
  The allocated buffer in which the operation parameter keys are written by the Security Source. [out]

- **dword keyBufferLength**  
  The capacity of the keyBuffer [in], the number of operation parameter keys in the keyBuffer. [out]

## Return Values

- **-11**  
  Operation Parameters are not supported by Vector Security Manager or used Security Source, you have to update to V2.5.7 or newer.

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)