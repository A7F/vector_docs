# lookupPdu

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dbPDU * lookupPDU(char pduName[]);
```

## Description

Searches for a PDU definition in the database(s). If the PDU is not found or if the name is not unique, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `dbPDU`.

**Notes**

It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.

## Parameters

- **pduName**: The qualified name of the PDU. The syntax is `[NetworkName::][NodeName::]PDUName`, i.e., both network name and node name are optional.

## Return Values

The found unique PDU definition or an invalid object.

## Example

See [Data Types for Variables](../../../Shared/CAPL/General/DataTypesForVariables.md#Database)
