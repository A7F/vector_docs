[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPConnectionClosedInd.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_ConnectionClosedInd

# _DoIP_ConnectionClosedInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void _DoIP_ConnectionClosedInd( long reason);
```

## Description

The TCP connection to the peer has been closed, i.e. another exchange of diagnostic messages will require a connection setup. This callback is also called in a vehicle simulation.

## Parameters

- **reason**  
  - `0`: The connection was closed by the node itself
  - `10054`: The peer closed the connection
  - Others: Reserved

## Return Values

—

## Example

```plaintext
void _DoIP_ConnectionClosedInd( long reason)
{
  write( "ConnectionClosedInd( %d)", reason);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)