[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionlookupSignal.md)

**CAPL Functions** » **General** » **Function Overview** » **lookupSignal**

# lookupSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `signal * lookupSignal(char signalName[]);` // form 1
- `signal * lookupSignal(dbSignal signal);` // form 2
- `signal * lookupSignal(dbSignal signal, dbNode node);` // form 3

## Description

Searches for a signal in the database(s). If the signal is not found or if the name is not unique, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `signal`.

**Notes:**

- It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.
- Use form 2 or 3 to program generically with a variable instead of accessing the value of the signal directly.
- Use form 3 if the signal is transmitted by several nodes in a bus system where the sender is important, like J1939.
- The reverse operation to form 2 or 3 is `DBLookup(signal).dbtype`.

## Parameters

- **signalName**: The qualified name of the signal. The syntax is `[Channel::][Database name (alias)::][Node::][Message::]Signal`; the order and completeness of the objects from right to left is important.

  **Note:**

  - Using drag and drop of a signal from the Symbol Explorer of the CAPL Browser results in a signal qualification where the database name is missing.
  - You must add the database name to the signal qualification at the correct order, so that the function could find the signal at runtime.

  See the example for [getSignal(char signalName[])](../../Test/Functions/CAPLfunctionGetSignal.htm).

- **signal**: The database signal.

- **node**: The transmitter node of the signal.

## Return Values

The found unique signal or an invalid object.

## Example

```plaintext
signal * sig;—
sig = lookupSignal("LightSwitch");
$sig = 1;
sig = lookupSignal(LightSwitch);
$sig = 0;
```

[Dynamic Search of Messages and Signals in Databases](../../../Shared/CAPL/General/DynamicSearchMessages.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)