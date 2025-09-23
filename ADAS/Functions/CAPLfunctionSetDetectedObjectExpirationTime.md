[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionSetDetectedObjectExpirationTime.md)

## SetDetectedObjectExpirationTime

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » SetDetectedObjectExpirationTime

### Valid for: CANoe DE

---

**Note**  
This CAPL function is also available as C# function.

### Function Syntax

**C#**  
`void SetDetectedObjectExpirationTime.Call(uint64 trackingId, uint64 time_ms);`

**CAPL**  
`void SetDetectedObjectExpirationTime.Call(uint64 trackingId, uint64 time_ms);`

### Description

This function can be used to set a detected object to state inactive that has been created by the SensorAPI. For deactivated detected objects the measurement state is set to Unknown and the object is not displayed anymore in the scene window's scene view. If the deactivated object receives data it again will be re-activated.

### Parameters

- **trackingId**: Id of the object to be deactivated
- **time_ms**: Time in milliseconds to deactivate the detected object, if it doesn’t receive data anymore. If the value is 0, the object will never be deactivated.

### Return Values

—

### Example

In the examples it is assumed in each case that a DO object of the type ISensor named **radar** is available.

#### CAPL

```plaintext
// Object with trackingId 5 is deactivated after 2000ms
radar.SetDetectedObjectExpirationTime.Call(5, 2000);
```

#### C#

```plaintext
// Object with trackingId 5 is deactivated after 2000ms
radar.SetDetectedObjectExpirationTime.Call(5, 2000);
```
