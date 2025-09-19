# Diagnostics: Basic CAPL Procedure for a Tester Implementation

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/CAPLfunctionsDiagnosticsTestImplementation.md)

**CAPL Functions** » **Diagnostics** » Basic CAPL Procedure for a Tester Implementation

**Valid for**: CANoe DE

This example explains how to implement:

- a CAPL test module for the test setup or
- a CAPL tester for the Simulation Setup

## Example (Syntax with ECU Qualifier in DiagRequest/Response Objects)

Starting with CANoe 9.0 SP3, the diagnostic target can be defined in the diagnostic object (DiagRequest or DiagResponse) by adding the ECU qualifier. The function [DiagSetTarget](Functions/CAPLfunctionDiagSetTarget.md) is no longer necessary.

### Create and send a request

```plaintext
diagRequest Door.SerialNumber_Read req;

DiagSendRequest(req);
```

### Changing the parameters of a request

```plaintext
diagRequest Door.SerialNumber_Write req;

diagSetParameter( req, "SerialNumber", 170821);
```

### Changing the raw parameters of a request

```plaintext
diagRequest Door.Coding_Write req;
byte rawData[2];

rawData[0] = 2500 / 256; // set raw data bytes
rawData[1] = 2500 % 256;
diagSetParameterRaw( req, "Parameter1", rawData, elcount(rawData));
```

### Reception of a response object, access to symbolic values

```plaintext
on diagResponse Door.Coding_Read {
   double out[1]; // numeric parameter
   char gValueString[2]; // Symbolic representation of the parameter value

   diagGetParameter( this, "Parameter2", out);
   diagGetParameter( this, "Parameter2", gValueString, elcount(gValueString));
}
```

### Reception of a timeout indication

```plaintext
{
   diagSetTimeoutHandler( "DefaultTimeoutHandler")
   diagSetTimeoutHandler( request1, "Request1TimeoutHandler");
}
DefaultTimeoutHandler() {
// ...
}
Request1TimeoutHandler() {
// ...
}
```

## Example (Deprecated Syntax)

### Selection of the target control device

```plaintext
diagSetTarget( "TestECU");
```

### Create and send a request

```plaintext
diagRequest CALIBRATION::Parametrierung::Lesen req;
DiagSendRequest(req);
```

### Changing the parameters of a request

```plaintext
diagRequest CALIBRATION::Parametrierung::Lesen req;
diagSetParameter( req, "Parameter1", 0.25);
rawData[0] = 2500 / 256; rawData[1] = 2500 % 256; // set raw data bytes
diagSetParameterRaw( req, "Parameter1", rawData, 2);
```

### Reception of a response object, access to symbolic values

```plaintext
on diagResponse CALIBRATION::Parametrierung::Lesen {
   double out[1]; // numeric parameter
   diagGetParameter( this, "Parameter2", out);
   // Symbolic representation of the parameter value.
   diagGetParameter( this, "Parameter2", gValueString, gStringLen);
}
```

### Reception of a timeout indication

```plaintext
{
   diagSetTimeoutHandler( "DefaultTimeoutHandler")
   diagSetTimeoutHandler( request1, "Request1TimeoutHandler");
}
DefaultTimeoutHandler() {
// ...
}
Request1TimeoutHandler() {
// ...
}
```

## Note

The length of the elements of a qualifier path from the CANdela description file is limited to 50 characters in the CAPL Compiler. Longer names may exceed this limit, but the CAPL program cannot be compiled. Nevertheless, it is possible to specify the qualifier path as a text string in quotation marks: "`<Qualifier Path>`". In this case, the qualifier path may be up to 255 characters in length.

[Connection of the Communication Layer](CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md) • [Basic CAPL Procedure for an ECU Implementation](CAPLfunctionsDiagnosticsECUImplementation.md) • [Expanded Functions in CAPL](CAPLfunctionsDiagnosticsExpandedFunctions.md)
