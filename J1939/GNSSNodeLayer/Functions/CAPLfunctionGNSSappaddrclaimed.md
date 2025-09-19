[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSappaddrclaimed.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSAppAddrClaimed

# GNSSAppAddrClaimed

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```markdown
void GNSSAppAddrClaimed();
```

## Description

Identifies an Address Claiming procedure that was performed successfully. In this manner the control device is able to communicate on the CAN bus. If the Address Claiming cannot be successfully performed, the [GNSSAppErrorIndication](CAPLfunctionGNSSapperrorindication.md) function is called with the corresponding error code.

## Parameters

—

## Return Values

—

## Example

```markdown
void GNSSAppAddrClaimed()
{
  write("Address Claiming was successful");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
