[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorConvertUnsignedToSigned.md)

**CAPL Functions** » **Sensor** » **sensorConvertUnsignedToSigned**

# sensorConvertUnsignedToSigned

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword sensorConvertUnsignedToSigned(dword inputSignalValue, long& outputSignalValue, dword bitCount);
```

## Description

Converts the given n bit input value from unsigned to signed using two's complement.

## Parameters

- **inputSignalValue**: The unsigned input value.
- **outputSignalValue**: The signed output value.
- **bitCount**: The length of the input/output signal in bits.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
dword inputValue = 13;
dword outputValue;

// Convert the 4 bit unsigned input value to a signed value
sensorConvertUnsignedToSigned(inputValue, outputValue, 4);

// outputValue is now -3.
```
