[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetOEMDataInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetOEMDataInd

# linGetOEMDataInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

```plaintext
long linGetOEMDataInd(); // form 1
long linGetOEMDataInd(char slaveName[]); // form 2
```

## Description

With this function it's possible to query the data indication bit of a Slave node. Without parameter, the data indication bit of the calling slave node is returned or zero if the caller is not a slave node.

## Parameters

- **slaveName**: Name of the queried Slave node as specified in the database.

## Return Values

- **-1**: Function call not allowed, execution failed or invalid slave name given.
- **0**: Queried data indication bit is not set.
- **>0**: Queried data indication bit is set.

## Example

—

[linCheckOEMDataInd](CAPLfunctionLINCheckOEMDataInd.md) • [linSetOEMDataInd](CAPLfunctionLINSetOEMDataInd.md) • [linSetOEMDataIndTime](CAPLfunctionLINSetOEMDataIndTime.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
