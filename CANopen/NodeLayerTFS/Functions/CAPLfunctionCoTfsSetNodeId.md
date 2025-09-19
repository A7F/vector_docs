# coTfsSetNodeId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
This function must be called before any other test function is called to provide the usage of the correct node-ID.

## Function Syntax

```plaintext
long coTfsSetNodeId( dword nodeID );
```

## Description

The internal node-ID for the simplified test functions is set.

## Parameters

- **nodeID**: 0 < node-ID < 128

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetNodeId (2); // set node-ID = 2
```
