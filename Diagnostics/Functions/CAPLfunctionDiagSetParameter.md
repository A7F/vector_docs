# diagSetParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

The behavior of this CAPL function depends on the used parameters.

Possible scenarios:

## Set the numeric parameter to the specified value

### Function Syntax

- `long diagSetParameter (diagResponse obj, char parameterName[], double newValue)`
- `long diagSetParameter (diagRequest obj, char parameterName[], double newValue)`
- `long diagSetParameter (diagResponse obj, long mode, char parameterName[], double newValue)`
- `long DiagSetParameter (diagRequest obj, long mode, char parameterName[], double newValue)`

### Method Syntax

- `diagResponse::SetParameter (char parameterName[], double newValue)`
- `diagRequest::SetParameter (char parameterName[], double newValue)`
- `diagResponse::SetParameter (long mode, char parameterName[], double newValue)`
- `diagRequest::SetParameter (long mode, char parameterName[], double newValue)`

### Description

Sets the numeric parameter to the specified value.

**Note**

- Textual diagnostic parameters cannot be set with double values.
- With **7.6 SP2** the function behavior was changed. The parameter will no longer be set to its default value.

### Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier (NOT the language-dependent name of the parameter!)
- **newValue**: Numeric value to which the parameter should be set.
- **[mode](../CAPLfunctionsDiagnosticsAccessMode.md)**: Access mode

### Return Values

- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example

```plaintext
variables {
  // Access modes for diagGet/SetParameter
  const long cParamAccessNumerical = 0;
  const long cParamAccessPhysical = 1;
  const long cParamAccessCoded = 2;

  // Parameter values
  const double cPhysicalValue = 14.2;
  const double cCodedValue = 11259375; // = 0xABCDEF
}

on key 's'
{
  diagRequest Door.WindowLiftRoughPosition_Write req;

  req.SetParameter("WindowLiftRoughPosition", "100,00%"); // set parameter to the symbolically-specified value
  req.SendRequest();
}

on key 'p'
{
  diagRequest ECU.Value1_Write req;

  diagSetParameter(req, cParamAccessPhysical, "PhysicalValue", cPhysicalValue);
  req.SendRequest(); // Parameter will be transmitted as 40 2C 66 66 66 66 66 66 (64bit double, Motorola format)
}

on key 'n'
{
  diagRequest ECU.Value2_Write req;
  double numericalValue;   // E.g. numerical value 142 would represent the same value as gPhysicalValue=14.2

  numericalValue=cPhysicalValue*10; // Based on formula, e.g. 142 * 1/10 = 14.2 (14.2 = physical value, 142 = numerical value)
  diagSetParameter(req, cParamAccessNumerical, "NumericalValue", numericalValue); // Set numerical value (e.g.: 142 equals 142 * 1/10 Volt = 14.2 Volt)

  req.SendRequest(); // Parameter will be transmitted as 0x40 0x61 0xBF 0xFF 0xFF 0xFF 0xFF 0xFF (64bit double, Motorola format)
}

on key 'c'
{
  diagRequest ECU.Value3_Write req;

  diagSetParameter(req, cParamAccessCoded, "Value_Uint32", cCodedValue); // Set coded value, not considering the byte order from diagnostic description (big or little endian)

  req.SendRequest(); // Parameter will be transmitted as 0x00 0xAB 0xCD 0xEF both for 32bit little endian parameters (Intel) and 32bit big endian parameters (Motorola)
}
```

## Set a parameter to the symbolically-specified value.

### Function Syntax

- `long diagSetParameter (diagResponse obj, char parameterName[], char newValue[])`
- `long diagSetParameter (diagRequest obj, char parameterName[], char newValue[])`

### Method Syntax

- `diagResponse::SetParameter (char parameterName[], char newValue[])`
- `diagRequest::SetParameter (char parameterName[], char newValue[])`

### Description

Sets a parameter to the symbolically-specified value. This is possible for all parameters, also numeric ones.

### Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **newValue**: Symbolic value

### Return Values

- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example

```plaintext
variables {
  // Access modes for diagGet/SetParameter
  const long cParamAccessNumerical = 0;
  const long cParamAccessPhysical = 1;
  const long cParamAccessCoded = 2;

  // Parameter values
  const double cPhysicalValue = 14.2;
  const double cCodedValue = 11259375; // = 0xABCDEF
}

on key 's'
{
  diagRequest Door.WindowLiftRoughPosition_Write req;

  req.SetParameter("WindowLiftRoughPosition", "100,00%"); // set parameter to the symbolically-specified value
  req.SendRequest();
}

on key 'p'
{
  diagRequest ECU.Value1_Write req;

  diagSetParameter(req, cParamAccessPhysical, "PhysicalValue", cPhysicalValue);
  req.SendRequest(); // Parameter will be transmitted as 40 2C 66 66 66 66 66 66 (64bit double, Motorola format)
}

on key 'n'
{
  diagRequest ECU.Value2_Write req;
  double numericalValue;   // E.g. numerical value 142 would represent the same value as gPhysicalValue=14.2

  numericalValue=cPhysicalValue*10; // Based on formula, e.g. 142 * 1/10 = 14.2 (14.2 = physical value, 142 = numerical value)
  diagSetParameter(req, cParamAccessNumerical, "NumericalValue", numericalValue); // Set numerical value (e.g.: 142 equals 142 * 1/10 Volt = 14.2 Volt)

  req.SendRequest(); // Parameter will be transmitted as 0x40 0x61 0xBF 0xFF 0xFF 0xFF 0xFF 0xFF (64bit double, Motorola format)
}

on key 'c'
{
  diagRequest ECU.Value3_Write req;

  diagSetParameter(req, cParamAccessCoded, "Value_Uint32", cCodedValue); // Set coded value, not considering the byte order from diagnostic description (big or little endian)

  req.SendRequest(); // Parameter will be transmitted as 0x00 0xAB 0xCD 0xEF both for 32bit little endian parameters (Intel) and 32bit big endian parameters (Motorola)
}
```
