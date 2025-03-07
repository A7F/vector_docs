[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimLoadLwATable.md)

# Iso11783IL_TIMLoadLwATable

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMLoadLwATable

**Valid for**: [CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMLoadLwATable(char iniFilePath[]); // form 1
long Iso11783IL_TIMLoadLwATable(dbNode participant, char iniFilePath[]); // form 2
```

## Description

Loads a table with lightweight authentication (LwA) keys from a file. The LwA table has to be stored with function [Iso11783IL_TIMSaveLwATable](CAPLfunctionIso11783ILtimSaveLwATable.md) before.

## Parameters

- **iniFilePath**: Path of a file (INI file format) which contains the LwA key table of the TIM client/server. Path has to be absolute or relative relating to the folder of the CANoe configuration.
- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)