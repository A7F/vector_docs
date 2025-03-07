[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionGetGroundTruthObjects.md)

# GetGroundTruthObjects

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » GetGroundTruthObjects

**Valid for**: CANoe DE

**Note**: This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
ADAS.GroundTruthObject_List GetGroundTruthObjects.Call();
```

**CAPL**

```capl
ADAS.GroundTruthObject_List GetGroundTruthObjects.Call();
```

## Description

Gets all ground truth objects as string-array.

## Parameters

—

## Return Values

A string array containing all available ground truth objects.

## Example

In the examples it is assumed in each case that a DO object of the type IGroundTruthAccess was created.

### CAPL

```capl
ADAS.GroundTruthObject_List = GroundTruthAccess.GetGroundTruthObjects().Call();
```

### C#

```csharp
ADAS.GroundTruthObject_List = GroundTruthAccess.GetGroundTruthObjects().Call();
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)