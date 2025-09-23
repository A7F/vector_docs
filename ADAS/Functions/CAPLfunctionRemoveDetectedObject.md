[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionRemoveDetectedObject.md)

## RemoveDetectedObject

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » RemoveDetectedObject

**Valid for**: CANoe DE

---

### Note

This CAPL function is also available in C#.

---

### Function Syntax

**C#**

```csharp
void RemoveDetectedObject.Call(int trackingId);
```

**CAPL**

```capl
void RemoveDetectedObject.Call(int trackingId);
```

### Description

This function can be used to remove a detected object from a sensor with a specific tracking Id.

### Parameters

- **trackingId**: Id of the object to be removed

### Return Values

—

### Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

#### CAPL

```capl
radar.RemoveDetectedObject.Call(5);
```

#### C#

```csharp
radar.RemoveDetectedObject.Call(5);
```
