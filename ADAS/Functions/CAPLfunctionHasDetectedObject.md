[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionHasDetectedObject.md)

## HasDetectedObject

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » HasDetectedObject

**Valid for:** CANoe DE

### Note
This CAPL function is also available in C#.

### Function Syntax

**C#**

```
bool HasDetectedObject.Call(int trackingId);
```

**CAPL**

```
int HasDetectedObject.Call(int trackingId);
```

### Description

This function can be used to query whether a detected object of a sensor with a specific tracking Id is present.

### Parameters

- **groundTruthId**: Id of the object

### Return Values

**C#**

- **true**: The object is available
- **false**: The object is not available

**CAPL**

- **1**: The object is available
- **0**: The object is not available

### Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

#### CAPL

```capl
int result = radar.HasDetectedObject.Call(5);
```

#### C#

```csharp
bool result = radar.HasDetectedObject.Call(5);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
