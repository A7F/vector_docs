[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionlookupMessage.md)

**CAPL Functions** » **General** » **Function Overview** » **lookupMessage**

# lookupMessage

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dbMsg * lookupMessage(char messageName[]);
```

## Description

Searches for a message definition in the database(s). If the message is not found or if the name is not unique, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `dbMsg`.

**Notes**

It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.

## Parameters

- **messageName**: The qualified name of the message. The syntax is `[NetworkName::][NodeName::]MessageName`, i.e., both network name and node name are optional.

## Return Values

The found unique message definition or an invalid object.

## Example

See [Data Types for Variables](../../../Shared/CAPL/General/DataTypesForVariables.md#Database)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
