[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783GetWSMaster.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783GetWSMaster

# Iso11783GetWSMaster

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783GetWSMaster(char busName[], dword ecuAddress);
```

## Description

This function returns the address of the Working Set Master, which is assigned to an ECU with the address **ecuAddress**.

## Parameters

- **busName**: Name of the bus
- **ecuAddress**: Address of an ECU

## Return Values

Address of the Working Set Master

## Example

```
wsmAddr = Iso11783GetWSMaster("default", 10);
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
