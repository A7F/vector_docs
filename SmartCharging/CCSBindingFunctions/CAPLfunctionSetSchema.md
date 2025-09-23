# SetSchema

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » SetSchema

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
MethodReturnValueType SetSchema (SchemaType SchemaToUse)
```

## Description

This function overwrites the schema used for encoding and decoding of V2G messages.

## Parameters

- **SchemaToUse**: Enum with following values:
  - 0 = Undefined
  - 1 = ISO20
  - 2 = ISO20_DC
  - 3 = ISO20_AC
  - 4 = ISO20_WPT

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- 0: OK
- 1: InvalidArgument
- 2: NoMatchingElementFound
- 3: UnknownError

## Example

—
