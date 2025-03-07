[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetAddress.md)

**CAPL Functions** » **J1939** » **Function Overview** » **J1939GetAddress**

# J1939GetAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939GetAddress (dbNode aNode);
```

## Description

Gets the current address of a J1939 node even if the address has been changed by the J1939 network management.

## Parameters

- **aNode**: The function returns the address of this node.

## Return Values

- **≥ 0**: Current address of the node.
- **-1**: General error, for example, node does not exist in database.

## Example

```c
dword address;
address = J1939GetAddress (N1);
Write("Address of node N1 is = %i", address );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)