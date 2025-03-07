[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionDeleteControlContent.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » DeleteControlContent

# DeleteControlContent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void DeleteControlContent(char[] panel, char[] control);
```

## Description

Deletes the content of the **CAPL Output View** in the *Panel Designer*. The panel is accessed by its individual panel name that is entered in the *Panel Designer*.

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels. If you open a panel the first time, the panel is loaded. If you close the panel, it remains loaded.
- **control**: Name of the CAPL Output View control, restricted to 128 characters. `""` – references all CAPL Output View controls on the panel.

## Return Values

— 

## Example

```plaintext
// Deletes the contents of a specific CAPL Output View control in the panel motor
DeleteControlContent("motor", "Outputview");

// Deletes the contents of all CAPL Output View controls in the panel motor
DeleteControlContent("motor", "");

// Deletes the contents of all CAPL Output View controls in all panels
DeleteControlContent("", "");
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)