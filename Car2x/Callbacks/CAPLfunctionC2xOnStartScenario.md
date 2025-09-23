[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Callbacks/CAPLfunctionC2xOnStartScenario.md)

## OnStartScenario (Callback)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » OnStartScenario

### Function Syntax

```plaintext
void OnStartScenario();
```

### Description

This callback is called at the time when the scenario start was triggered:

- manually in Scenario Manager Window;
- as a result of calling [C2xStartScenario()](../Functions/CAPLfunctionC2xStartScenario.md) CAPL function.

### Parameters

—

### Return Values

—

### Example

```plaintext
void OnStartScenario()
{
    write("Station '%NODE_NAME%': %f sec - OnStartScenario was called" , TimeNowNS()/1e9);
    write("Station '%NODE_NAME%': OnStartScenario - Station Speed = %f", C2xGetStationAttributeDouble("Speed"));
}
```
