[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionHasGroundTruthObject.md)

# HasGroundTruthObject

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » HasGroundTruthObject

**Valid for**: CANoe DE

---

### Note

This CAPL function is also available in C#.

---

## Function Syntax

**C#**

```csharp
bool HasGroundTruthObject.Call(uint64 groundTruthId);
```

**CAPL**

```capl
int HasGroundTruthObject.Call(uint64 groundTruthId);
```

## Description

Checks if a ground truth object with a special ground truth id exists.

## Parameters

- **uint64 groundTruthId**: The id of the ground truth object

## Return Values

True if the object exists, else false.

## Example

In the examples it is assumed in each case that a DO object of the type IGroundTruthAccess was created.

### CAPL

```capl
int groundTruthObjectAvailable = GroundTruthAccess.HasGroundTruthObject.Call(42);
```

### C#

```csharp
bool groundTruthObjectAvailable = GroundTruthAccess.HasGroundTruthObject.Call(42);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)