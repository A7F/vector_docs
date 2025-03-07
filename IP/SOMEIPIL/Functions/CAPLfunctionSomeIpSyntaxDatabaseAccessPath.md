[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **Syntax for Database-based Access Paths**

# Syntax for Database-based Access Paths

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

A value path is used to access parameters of a SOME/IP Message with [SomeIpGetValue...](CAPLfunctionSomeIpGetValue.md) and [SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md).

The path begins with a SOME/IP parameter name. Arrays of a struct/unions are selected with **Name**, arrays of arrays are selected with **[Index]**.

**Example**

```
paramName.memberName.twoDimArray[1][2].fieldName
```

## Parameter

- **GetValue(path, int32) / GetValue(path, int64)**
  - **Type**: Boolean, Integer, Enumerated
  - **Description**: Array value
  - **Type**: Union
  - **Description**: Index of the sub-element
  - **Type**: Array
  - **Description**: Number of sub-elements

- **GetValue(path, double)**
  - **Type**: Float, Double
  - **Description**: Array value

- **GetValue(path, len, buffer)**
  - **Type**: Enumerated
  - **Description**: Symbolic value of the array
  - **Type**: String
  - **Description**: Array value
  - **Type**: Union
  - **Description**: Name of the current sub-element

- **SetValue(path, int32) / SetValue(path, int64)**
  - **Type**: Boolean, Integer, Enumerated
  - **Description**: Array value

- **SetValue(path, double)**
  - **Type**: Float, Double
  - **Description**: Array value

- **SetValue(path, len, buffer)**
  - **Type**: Enumerated
  - **Description**: Symbolic value of the array
  - **Type**: String
  - **Description**: Array value

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)