[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/CAPLfunctionsDiagnosticsECUImplementation.md)

## CAPL Functions » Diagnostics » Basic CAPL Procedure for an ECU Implementation

### Diagnostics: Basic CAPL Procedure for an ECU Implementation

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

### Preparation

On the configuration dialog of the diagnostic observer, a description must be assigned to the simulation node!

**Example**

The CAPL program waits for requests from the tester and can then send a response:

```plaintext
on diagRequest Door.SerialNumber_Read {
   DiagResponse this resp;
   DiagSetParameter( resp, "SerialNumber", 170821);
   DiagSendResponse( resp);
}
```

It is possible to react to several requests:

```plaintext
on diagRequest Door.EcuReset::* {        // Handle soft and hard reset
   DiagSendNegativeResponse( this, 0x11); // SNS Service not supported
}
```

Here the method which qualifier path has the longest match with that of the object will be called.

**Note**

The length of the elements of a qualifier path from the CANdela description file is limited to 50 characters in the CAPL Compiler. Longer names may exceed this limit, but the CAPL program cannot be compiled. Nevertheless, it is possible to specify the qualifier path as a text string in quotation marks: "`<Qualifier Path>`". In this case the qualifier path may be up to 255 characters in length.

[Connection of the Communication Layer](CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md) • [Basic CAPL Procedure for a Tester Implementation](CAPLfunctionsDiagnosticsTestImplementation.md) • [Expanded Functions in CAPL](CAPLfunctionsDiagnosticsExpandedFunctions.md)
