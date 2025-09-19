# GetGroundTruthObject

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » GetGroundTruthObject

**Valid for**: CANoe DE

**Note**: This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
string GetGroundTruthObject.Call(uint64 groundTruthId);
```

**CAPL**

```capl
ADAS.GroundTruthObject_List GetGroundTruthObject.Call(uint64 groundTruthId);
```

## Description

Gets ground truth object as string by a ground truth id.

## Parameters

- **uint64 groundTruthId**: The id of the ground truth object

## Return Values

The name of the ground truth object as string.

## Example

In the examples it is assumed in each case that a DO object of the type IGroundTruthAccess was created.

### CAPL

```capl
char groundTruthObjName [100];
memcpy(groundTruthObjName, GroundTruthAccess.GetGroundTruthObject.Call(5), elCount(GroundTruthAccess.GetGroundTruthObject.Call(5));
```

### C#

```csharp
string groundTruthObjectName = GroundTruthAccess.GetGroundTruthObject.Call(42);
// The Ground Truth object (IEnvironmentObject) can be retrieved from DORegistry-interface
_ADAS.DataModel.IEnvironmentObject envObject = DORegistry.LookupDistributedObject<_ADAS.DataModel.IEnvironmentObject>(groundTruthObject, "ADAS");
```
