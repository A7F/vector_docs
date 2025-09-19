[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGraphicsWindowModifyGroup.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » graphicsWindowModifyGroup

# graphicsWindowModifyGroup

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void graphicsWindowModifyGroup(char[] windowName, byte mode, char[] groupName);
```

## Description

Modifies group enabled and expanded states.

## Parameters

- **windowName**: The name of the Graphics Window.
- **byte mode**:
  - 1 = Enable group
  - 2 = Disable group
  - 3 = Expand group
  - 4 = Collapse group
  - 5 = Disable all groups
  - 6 = Collapse all groups
  - 7 = Expand all enabled groups
  - 8 = Collapse all disabled groups
- **groupName**: The name of the common axis/group to modify (optional parameter).

## Return Values

—

## Example

```c
// Expand a group
graphicsWindowModifyGroup("Graphics", 3, "MyGroup");

// Disable all groups
graphicsWindowModifyGroup("Graphics", 5);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
