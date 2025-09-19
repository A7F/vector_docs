[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionsysGetVariableSVType.md)

## sysGetVariableSVType

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableSVType

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```
long sysGetVariableSVType(sysvar);
```

### Description

Gets the type of a system variable encoded as a long integer.

### Parameters

- **sysvar**: A value of type system variable.

### Return Values

- **0**: Invalid
- **1**: Double (64 Bit)
- **2**: Integer (32 Bit)
- **3**: String
- **4**: Double Array
- **5**: Integer Array
- **6**: Integer (64 Bit)
- **7**: Data

### Example

```c
long t1, t2;
t1 = sysGetVariableSVType(lookupSysvar("mysysvar"));
t2 = sysGetVariableSVType(sysvar::mysysvar);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
