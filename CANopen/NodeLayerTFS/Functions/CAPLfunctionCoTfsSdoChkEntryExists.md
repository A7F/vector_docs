# coTfsSDOChkEntryExists (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOChkEntryExists( dword index, dword subindex );
```

## Description

This function checks with a SDO upload if the object is readable.

## Parameters

- **index**: Object index in the object dictionary.
- **subindex**: Object subindex in the object dictionary.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md) or one of the following values:

- 2: received abort code 0x06010001 (attempt to read a write only object)
- 3: received abort code 0x06090011, 0x06020000 or 0x08000000
- 4: received an unexpected abort code
- 5: received more than one abort code
- 6: error during SDO access
- 7: time-out

## Example

```plaintext
/* check if object [1000,0] is readable. This function is mainly a SDO upload function, but the test report output differs to make it more useful to check if an optional object exists */
if (coTfsSDOChkEntryExists(0x1000, 0) != 1)
{
  /* entry does not exist, 0x1000 is mandatory, so something serious is wrong here */
} /* if */
```
