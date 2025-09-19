[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestILSetMessageProperty.md)

**CAPL Functions** » **Test Feature Set** » **testILSetMessageProperty**

# testILSetMessageProperty

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testILSetMessageProperty(dbNode node, dbMsg msg, char propertyName[], long propertyValue);
```

## Description

Sets the internal property of a message, assigned to the node.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **node**: Node name as defined in the database.
- **msg**: Message name as defined in the database.
- **propertyName**: Name of property to be set.
  - **Value**: Description
    - **MessageCounterToContinue**: Defines the next value of the intern message counter that will be sent. Applicable for the PGNs 0, 1024, 2816, 61469 and 61483 only (see [Message Checksum and Message Counter](../../../CANoeCANalyzer/J1939/j1939IL/j1939ILErrorDetection.md)). Valid values for **propertyValue** are 0 to 7 (PGN = 0) or 0 to 15 (all other applicable PGNs).
    - **DA**: Sets the message destination address.
    - **Priority**: Sets the message priority.
    - **DelayTime**: Sets the message delay time in ms.
- **propertyValue**: New value to be set for the property.

## Return Values

- **0**: Success (property has been set successfully)
- **< 0**: [Error codes](../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
if (testILSetMessageProperty(EBS, TSC1, "MessageCounterToContinue", 12) < 0)
{
  write("Can’t set message property ‘MessageCounterToContinue‘");
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
