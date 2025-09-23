[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSaveLwATable.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMSaveLwATable

# Iso11783IL_TIMSaveLwATable

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSaveLwATable(char iniFilePath); // form 1
long Iso11783IL_TIMSaveLwATable(dbNode participant, char iniFilePath[]); // form 2
```

## Description

Stores the table with lightweight authentication (LwA) keys in a file.  
You can load the stored LwA table with function Iso11783IL_TIMLoadLwATable.

## Parameters

- **iniFilePath**: Path of a file (INI file format) which stores the LwA key table of the TIM client/server. Path has to be absolute or relative relating to the folder of the CANoe configuration.
- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
