# coTfsNodeGuarding (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsNodeGuarding( dword maxResponseTime );
```

## Description

After that, 20 guarding remote frames are sent to the target device. The target device must respond to all queries within the `maxResponseTime`.

## Parameters

- **maxResponseTime**: Maximum permissible response time in milliseconds.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsNodeGuarding (40) != 1) {  // maxResponseTime
  write("Node guarding test failed");
}
```
