# GetDetectedObjectsCondtional

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
ADAS.DetectedObject_List GetDetectedObjectsConditional.Call_Phys(_ADAS.ECriterion criterionType, double conditionValue, _ADAS.ETriggerCondition conditionBelowOrAbove);
```

**CAPL**

```capl
ADAS.DetectedObject_List GetDetectedObjectsConditional.Call_Phys(_ADAS::DataModel::ECriterion criterionType, double conditionValue, _ADAS::DataModel::ETriggerCondition conditionBelowOrAbove)
```

## Description

Gets the detected objects of a sensor as a string array. Only those objects are considered that meet the condition passed in the parameters. Possible conditions are a distance and a relative speed to the sensor above or below a certain value.

## Parameters

- **criterionType**: Type of the condition.
  - **C#**
    - `_ADAS.DataModel.ECriterion.Distance`
    - `_ADAS.DataModel.ECriterion.Speed`
  - **CAPL**
    - `_ADAS::DataModel::ECriterion::Distance`
    - `_ADAS::DataModel::ECriterion::Speed`

- **conditionValue**: Limit value of the condition

- **conditionBelowOrAbove**: Indicates whether the value must be above or below the limit value
  - **C#**
    - `_ADAS.DataModel.ETriggerCondition.Lesser`
    - `_ADAS.DataModel.ETriggerCondition.Greater`
  - **CAPL**
    - `_ADAS.DataModel::ETriggerCondition::Lesser`
    - `_ADAS.DataModel::ETriggerCondition::Greater`

## Return Values

A string array containing all detected objects of the sensor which meet the conditions passed in the parameters.

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
int countDetObj = 0;
ADAS.DetectedObject_List detObjNames = radar.GetDetectedObjectsConditional.Call_Phys(
  ADAS::DataModel::ECriterion::Distance, 70.0, _ADAS::DataModel::ETriggerCondition::Lesser);
countDetObj = elCount(detObjNames);
if(countDetObj == 1)
{
  write("An ADAS Object with a Distance lesser than 70.0m has been detected");
}
```

### C#

```csharp
ADAS.DetectedObject_List detObjNames = radar.GetDetectedObjectsConditional.Call_Phys(
  _ADAS.DataModel.ECriterion.Distance, 70.0, _ADAS.DataModel.ETriggerCondition.Lesser);
if (detObjNames.Length == 1)
{
  Output.WriteLine("An ADAS Object with a Distance lesser than 70.0m has been detected");
}
```
