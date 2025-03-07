[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetOEMSleepInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetOEMSleepInd

# linGetOEMSleepInd

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

**Note**  
This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

```plaintext
long linGetOEMSleepInd(); // form 1
long linGetOEMSleepInd(char slaveName[]); // form 2
```

## Description

With this function it's possible to query the sleep indication bit of a Slave node. Without parameter, the sleep indication bit of the calling slave is returned or zero if the caller is not a slave.

## Parameters

- **slaveName**: Name of the queried Slave node as specified in the database.

## Return Values

- **-1**: Function call not allowed, execution failed or invalid slave name given.
- **0**: Queried sleep indication bit is not set.
- **>0**: Queried sleep indication bit is set.

## Example

—

[linCheckOEMSleepInd](CAPLfunctionLINCheckOEMSleepInd.md) • [linSetOEMSleepInd](CAPLfunctionLINSetOEMSleepInd.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)