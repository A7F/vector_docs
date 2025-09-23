[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionParseEndpointFromString.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **IP_Endpoint::ParseEndpointFromString**

# IP_Endpoint::ParseEndpointFromString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long IP_Endpoint::ParseEndpointFromString(char endpoint[]);
```

## Description

Converts the character string to an endpoint and sets this endpoint to the IP endpoint value.

## Parameters

- **endpoint**: A character string representing an IP endpoint.

## Return Values

- **0**: Success
- **1**: Parser error

## Example

```plaintext
variables
{
  ip_Endpoint ipEndpoint;
}

on sysvar_update sysvar::Endpoint
{
  char endpointText[60];
  sysGetVariableString(this, endpointText, elcount(endpointText));
  ipEndpoint.ParseEndpointFromString(endpointText);
}
```
