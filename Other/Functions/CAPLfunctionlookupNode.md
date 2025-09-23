# lookupNode

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dbNode * lookupNode(char nodeName[]);
```

## Description

Searches for a node definition in the database(s). If the node is not found or if the name is not unique, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `dbNode`.

**Notes**: It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.

## Parameters

- **nodeName**: The qualified name of the node. The syntax is `[NetworkName::]NodeName`, i.e. the network name is optional.

## Return Values

The found unique node definition or an invalid object.

## Example

See [Data Types for Variables](../../../Shared/CAPL/General/DataTypesForVariables.md#Database)
