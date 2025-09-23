# SetCustomCRCCalculation

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Function Syntax

```plaintext
SensorErrorCode sysvarSensorNamespace.SetCustomCRCCalculation(char[] callbackFctName);
```

## Description

Set a callback for custom defined CRC calculation algorithm.

## Parameters

- **callbackFctName**: The name of the CAPL callback function (See example for function signature).

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
on preStart
{
  enum sensorErrorCode result;
  // Set custom crc calculation algorithm
  result = sysvar::SENSOR::SENT::SensorSim::Sensor.SetCustomCRCCalculation("SentCustomCrcCallback");
  if (result == eSensorNoError)
  {
    write("Setting custom crc algorithm succeeded.");
  }
  else
  {
    write("Setting custom crc algorithm failed with code: %d", result);
  }
}

dword SentCustomCrcCallback(dword statusNibble, dword dataNibbles, dword dataNibbleCount)
{
  dword i;
  dword crc;
  crc = statusNibble & 0xF;
  for (i = 0; i < dataNibbleCount; i++)
  {
    crc ^= (dataNibbles >> i * 4) & 0xF;
  }
  return crc;
}
```
