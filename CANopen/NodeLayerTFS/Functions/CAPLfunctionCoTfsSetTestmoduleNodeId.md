# coTfsSetTestModuleNodeId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
This function shall **not** be used if a [CiA®](javascript:void(0)) 301 compliant device is tested!

## Function Syntax

```plaintext
long coTfsSetTestModuleNodeId( dword nodeId );
```

## Description

The function set the node-ID of the tester. This is particularly necessary for the application profile. The function has to be called before the first use of SDOs.

## Parameters

- **nodeId**: Node-ID of the tester, if application profile 447 is used the valid range is 1..16.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetTestModuleNodeId(15); // set node-ID to 15
```
